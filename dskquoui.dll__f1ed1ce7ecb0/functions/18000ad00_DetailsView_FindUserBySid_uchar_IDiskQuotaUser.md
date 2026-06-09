# DetailsView::FindUserBySid(uchar *,IDiskQuotaUser * *)

- ea: `0x18000ad00`
- end: `0x18000adeb`
- name: `?FindUserBySid@DetailsView@@AEAAHPEAEPEAPEAUIDiskQuotaUser@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(DetailsView *__hidden this, unsigned __int8 *, struct IDiskQuotaUser **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b8fc`

## callees

- `0x180001510`
- `0x18000ad00`
- `0x180011160`
- `0x1800112e8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000adc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000adc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad3d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ada4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ada4`

## pseudocode

```c
__int64 __fastcall DetailsView::FindUserBySid(DetailsView *this, unsigned __int8 *a2, struct IDiskQuotaUser **a3)
{
  unsigned int v4; // esi
  char *v5; // r15
  signed int v6; // r13d
  signed int v7; // ebx
  struct IDiskQuotaUser *v8; // rdi
  void *v10; // [rsp+20h] [rbp-B8h] BYREF
  PSID pSid2; // [rsp+28h] [rbp-B0h]
  DetailsView *v12; // [rsp+30h] [rbp-A8h]
  _BYTE pSid1[80]; // [rsp+40h] [rbp-98h] BYREF

  pSid2 = a2;
  v12 = this;
  v4 = -1;
  v5 = (char *)this + 40;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v6 = StructureList::Count((StructureList *)v5);
  v10 = 0;
  v7 = 0;
  while ( v7 < v6 && v4 == -1 )
  {
    try
    {
      if ( PointerList::Retrieve((PointerList *)v5, &v10, v7) )
      {
        v8 = (struct IDiskQuotaUser *)v10;
        if ( v10 )
        {
          (*(void (__fastcall **)(void *, _BYTE *, __int64))(*(_QWORD *)v10 + 48LL))(v10, pSid1, 68);
          if ( EqualSid(pSid1, pSid2) )
          {
            v4 = v7;
            if ( a3 )
              *a3 = v8;
          }
        }
      }
      ++v7;
    }
    catch ( CAllocException )
    {
      PointerList::ReleaseLock((DetailsView *)((char *)v12 + 40));
      throw;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
  return v4;
}

```

## disassembly

```asm
0x18000ad00  push    rbx
0x18000ad02  push    rsi
0x18000ad03  push    rdi
0x18000ad04  push    r12
0x18000ad06  push    r13
0x18000ad08  push    r14
0x18000ad0a  push    r15
0x18000ad0c  sub     rsp, 0A0h
0x18000ad13  mov     rax, cs:__security_cookie
0x18000ad1a  xor     rax, rsp
0x18000ad1d  mov     [rsp+0D8h+var_48], rax
0x18000ad25  mov     r14, r8
0x18000ad28  mov     [rsp+0D8h+pSid2], rdx
0x18000ad2d  mov     [rsp+0D8h+var_A8], rcx
0x18000ad32  or      esi, 0FFFFFFFFh
0x18000ad35  lea     r15, [rcx+28h]
0x18000ad39  lea     rcx, [r15+10h]; lpCriticalSection
0x18000ad3d  call    cs:__imp_EnterCriticalSection
0x18000ad43  nop
0x18000ad44  mov     rcx, r15; this
0x18000ad47  call    ?Count@StructureList@@QEAAIXZ; StructureList::Count(void)
0x18000ad4c  mov     r13d, eax
0x18000ad4f  mov     [rsp+0D8h+var_B8], 0
0x18000ad58  xor     ebx, ebx
0x18000ad5a  cmp     ebx, r13d
0x18000ad5d  jge     short loc_18000ADBC
0x18000ad5f  cmp     esi, 0FFFFFFFFh
0x18000ad62  jnz     short loc_18000ADBC
0x18000ad64  mov     r8d, ebx; unsigned int
0x18000ad67  lea     rdx, [rsp+0D8h+var_B8]; void **
0x18000ad6c  mov     rcx, r15; this
0x18000ad6f  call    ?Retrieve@PointerList@@QEAAHPEAPEAXI@Z; PointerList::Retrieve(void * *,uint)
0x18000ad74  test    eax, eax
0x18000ad76  jz      short loc_18000ADB8
0x18000ad78  mov     rdi, [rsp+0D8h+var_B8]
0x18000ad7d  test    rdi, rdi
0x18000ad80  jz      short loc_18000ADB8
0x18000ad82  mov     rax, [rdi]
0x18000ad85  lea     r8d, [rsi+45h]
0x18000ad89  lea     rdx, [rsp+0D8h+pSid1]
0x18000ad8e  mov     rcx, rdi
0x18000ad91  mov     rax, [rax+30h]
0x18000ad95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad9a  mov     rdx, [rsp+0D8h+pSid2]; pSid2
0x18000ad9f  lea     rcx, [rsp+0D8h+pSid1]; pSid1
0x18000ada4  call    cs:__imp_EqualSid
0x18000adaa  test    eax, eax
0x18000adac  jz      short loc_18000ADB8
0x18000adae  mov     esi, ebx
0x18000adb0  test    r14, r14
0x18000adb3  jz      short loc_18000ADB8
0x18000adb5  mov     [r14], rdi
0x18000adb8  inc     ebx
0x18000adba  jmp     short loc_18000AD5A
0x18000adbc  lea     rcx, [r15+10h]; lpCriticalSection
0x18000adc0  call    cs:__imp_LeaveCriticalSection
0x18000adc6  mov     eax, esi
0x18000adc8  mov     rcx, [rsp+0D8h+var_48]
0x18000add0  xor     rcx, rsp; StackCookie
0x18000add3  call    __security_check_cookie
0x18000add8  add     rsp, 0A0h
0x18000addf  pop     r15
0x18000ade1  pop     r14
0x18000ade3  pop     r13
0x18000ade5  pop     r12
0x18000ade7  pop     rdi
0x18000ade8  pop     rsi
0x18000ade9  pop     rbx
0x18000adea  retn
```
