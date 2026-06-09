# DetailsView::FindUserByName(ushort const *,IDiskQuotaUser * *)

- ea: `0x18000abe4`
- end: `0x18000acf7`
- name: `?FindUserByName@DetailsView@@AEAAHPEBGPEAPEAUIDiskQuotaUser@@@Z`
- size: `275`
- prototype: `int(DetailsView *__hidden this, const unsigned __int16 *, struct IDiskQuotaUser **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001058c`

## callees

- `0x180001510`
- `0x18000abe4`
- `0x180011160`
- `0x1800112e8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000acb0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000acb0`

## pseudocode

```c
__int64 __fastcall DetailsView::FindUserByName(
        DetailsView *this,
        const unsigned __int16 *a2,
        struct IDiskQuotaUser **a3)
{
  unsigned int v4; // edi
  char *v5; // rsi
  signed int v6; // r15d
  signed int v7; // ebx
  void *v9; // [rsp+40h] [rbp-258h] BYREF
  DetailsView *v10; // [rsp+48h] [rbp-250h]
  WCHAR String1[264]; // [rsp+50h] [rbp-248h] BYREF

  v10 = this;
  v4 = -1;
  v5 = (char *)this + 40;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v6 = StructureList::Count((StructureList *)v5);
  v9 = 0;
  v7 = 0;
  while ( v7 < v6 && v4 == -1 )
  {
    try
    {
      if ( PointerList::Retrieve((PointerList *)v5, &v9, v7) )
      {
        if ( v9 )
        {
          (*(void (__fastcall **)(void *, _QWORD, _QWORD, WCHAR *, int, _QWORD, _DWORD))(*(_QWORD *)v9 + 32LL))(
            v9,
            0,
            0,
            String1,
            260,
            0,
            0);
          if ( CompareStringW(0x400u, 1u, String1, -1, a2, -1) == 2 )
            v4 = v7;
        }
      }
      ++v7;
    }
    catch ( CAllocException )
    {
      PointerList::ReleaseLock((DetailsView *)((char *)v10 + 40));
      throw;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
  return v4;
}

```

## disassembly

```asm
0x18000abe4  mov     [rsp+arg_10], rbx
0x18000abe9  push    rsi
0x18000abea  push    rdi
0x18000abeb  push    r12
0x18000abed  push    r14
0x18000abef  push    r15
0x18000abf1  sub     rsp, 270h
0x18000abf8  mov     rax, cs:__security_cookie
0x18000abff  xor     rax, rsp
0x18000ac02  mov     [rsp+298h+var_38], rax
0x18000ac0a  mov     r12, rdx
0x18000ac0d  mov     [rsp+298h+var_250], rcx
0x18000ac12  or      edi, 0FFFFFFFFh
0x18000ac15  lea     rsi, [rcx+28h]
0x18000ac19  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000ac1d  call    cs:__imp_EnterCriticalSection
0x18000ac23  nop
0x18000ac24  mov     rcx, rsi; this
0x18000ac27  call    ?Count@StructureList@@QEAAIXZ; StructureList::Count(void)
0x18000ac2c  mov     r15d, eax
0x18000ac2f  mov     [rsp+298h+var_258], 0
0x18000ac38  xor     ebx, ebx
0x18000ac3a  cmp     ebx, r15d
0x18000ac3d  jge     loc_18000ACC3
0x18000ac43  cmp     edi, 0FFFFFFFFh
0x18000ac46  jnz     short loc_18000ACC3
0x18000ac48  mov     r8d, ebx; unsigned int
0x18000ac4b  lea     rdx, [rsp+298h+var_258]; void **
0x18000ac50  mov     rcx, rsi; this
0x18000ac53  call    ?Retrieve@PointerList@@QEAAHPEAPEAXI@Z; PointerList::Retrieve(void * *,uint)
0x18000ac58  test    eax, eax
0x18000ac5a  jz      short loc_18000ACBC
0x18000ac5c  mov     rcx, [rsp+298h+var_258]
0x18000ac61  test    rcx, rcx
0x18000ac64  jz      short loc_18000ACBC
0x18000ac66  mov     rax, [rcx]
0x18000ac69  mov     [rsp+298h+var_268], 0
0x18000ac71  mov     qword ptr [rsp+298h+cchCount2], 0
0x18000ac7a  mov     dword ptr [rsp+298h+lpString2], 104h
0x18000ac82  lea     r9, [rsp+298h+String1]
0x18000ac87  xor     r8d, r8d
0x18000ac8a  xor     edx, edx
0x18000ac8c  mov     rax, [rax+20h]
0x18000ac90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac95  or      eax, edi
0x18000ac97  mov     [rsp+298h+cchCount2], eax; cchCount2
0x18000ac9b  mov     [rsp+298h+lpString2], r12; lpString2
0x18000aca0  mov     r9d, eax; cchCount1
0x18000aca3  lea     r8, [rsp+298h+String1]; lpString1
0x18000aca8  lea     edx, [rdi+2]; dwCmpFlags
0x18000acab  mov     ecx, 400h; Locale
0x18000acb0  call    cs:__imp_CompareStringW
0x18000acb6  cmp     eax, 2
0x18000acb9  cmovz   edi, ebx
0x18000acbc  inc     ebx
0x18000acbe  jmp     loc_18000AC3A
0x18000acc3  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000acc7  call    cs:__imp_LeaveCriticalSection
0x18000accd  mov     eax, edi
0x18000accf  mov     rcx, [rsp+298h+var_38]
0x18000acd7  xor     rcx, rsp; StackCookie
0x18000acda  call    __security_check_cookie
0x18000acdf  mov     rbx, [rsp+298h+arg_10]
0x18000ace7  add     rsp, 270h
0x18000acee  pop     r15
0x18000acf0  pop     r14
0x18000acf2  pop     r12
0x18000acf4  pop     rdi
0x18000acf5  pop     rsi
0x18000acf6  retn
```
