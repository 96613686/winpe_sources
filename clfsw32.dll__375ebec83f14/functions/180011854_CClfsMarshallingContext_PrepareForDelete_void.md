# CClfsMarshallingContext::PrepareForDelete(void)

- ea: `0x180011854`
- end: `0x180011955`
- name: `?PrepareForDelete@CClfsMarshallingContext@@QEAAKXZ`
- size: `257`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000aaa0`

## callees

- `0x18000efa0`
- `0x18000fcdc`
- `0x1800101c8`
- `0x180011854`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001189e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800118d9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800118e7`
- `ntdll!RtlLeaveCriticalSection` at `0x180011921`
- `ntdll!RtlLeaveCriticalSection` at `0x18001189e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800118d9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800118e7`
- `ntdll!RtlLeaveCriticalSection` at `0x180011921`
- `ntdll!RtlEnterCriticalSection` at `0x180011870`
- `ntdll!RtlEnterCriticalSection` at `0x180011886`
- `ntdll!RtlEnterCriticalSection` at `0x180011870`
- `ntdll!RtlEnterCriticalSection` at `0x180011886`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::PrepareForDelete(CClfsMarshallingContext *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  __int64 v4; // rdx
  bool v5; // zf
  union _CLS_LSN v7; // [rsp+30h] [rbp+8h] BYREF
  union _CLS_LSN v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 248));
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  if ( *((_DWORD *)this + 58) )
  {
    RtlLeaveCriticalSection(v3);
  }
  else
  {
    RtlLeaveCriticalSection(v3);
    v4 = *((_QWORD *)this + 20);
    if ( !v4 )
    {
LABEL_6:
      RtlLeaveCriticalSection(v1);
      return 0;
    }
    if ( !*(_DWORD *)(v4 + 76) && !*(_QWORD *)(v4 + 80) )
    {
      CClfsMarshallingContext::FreeIocb(this, (struct CLogIocb *)v4);
      *((_QWORD *)this + 20) = 0;
      goto LABEL_6;
    }
  }
  v5 = *((_QWORD *)this + 20) == 0;
  v8 = CLFS_LSN_NULL;
  v7 = CLFS_LSN_NULL;
  if ( !v5 )
    CClfsMarshallingContext::AppendWriteBlockToFlushQueue(this, 1, 0, 0);
  RtlLeaveCriticalSection(v1);
  CClfsMarshallingContext::FlushToLsn(this, &v8, &v7, 0);
  return 0;
}

```

## disassembly

```asm
0x180011854  mov     [rsp+arg_10], rbx
0x180011859  mov     [rsp+arg_18], rsi
0x18001185e  push    rdi
0x18001185f  sub     rsp, 20h
0x180011863  lea     rsi, [rcx+148h]
0x18001186a  mov     rbx, rcx
0x18001186d  mov     rcx, rsi; CriticalSection
0x180011870  call    cs:__imp_RtlEnterCriticalSection
0x180011877  nop     dword ptr [rax+rax+00h]
0x18001187c  lea     rdi, [rbx+0F8h]
0x180011883  mov     rcx, rdi; CriticalSection
0x180011886  call    cs:__imp_RtlEnterCriticalSection
0x18001188d  nop     dword ptr [rax+rax+00h]
0x180011892  cmp     dword ptr [rbx+0E8h], 0
0x180011899  mov     rcx, rdi; CriticalSection
0x18001189c  jnz     short loc_1800118E7
0x18001189e  call    cs:__imp_RtlLeaveCriticalSection
0x1800118a5  nop     dword ptr [rax+rax+00h]
0x1800118aa  mov     rdx, [rbx+0A0h]; struct CLogIocb *
0x1800118b1  test    rdx, rdx
0x1800118b4  jz      short loc_1800118D6
0x1800118b6  cmp     dword ptr [rdx+4Ch], 0
0x1800118ba  ja      short loc_1800118F3
0x1800118bc  cmp     qword ptr [rdx+50h], 0
0x1800118c1  jnz     short loc_1800118F3
0x1800118c3  mov     rcx, rbx; this
0x1800118c6  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x1800118cb  mov     qword ptr [rbx+0A0h], 0
0x1800118d6  mov     rcx, rsi; CriticalSection
0x1800118d9  call    cs:__imp_RtlLeaveCriticalSection
0x1800118e0  nop     dword ptr [rax+rax+00h]
0x1800118e5  jmp     short loc_180011942
0x1800118e7  call    cs:__imp_RtlLeaveCriticalSection
0x1800118ee  nop     dword ptr [rax+rax+00h]
0x1800118f3  cmp     qword ptr [rbx+0A0h], 0
0x1800118fb  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x180011902  mov     qword ptr [rsp+28h+arg_8], rax
0x180011907  mov     qword ptr [rsp+28h+arg_0], rax
0x18001190c  jz      short loc_18001191E
0x18001190e  xor     r9d, r9d; struct _OVERLAPPED *
0x180011911  xor     r8d, r8d; unsigned int
0x180011914  mov     dl, 1; unsigned __int8
0x180011916  mov     rcx, rbx; this
0x180011919  call    ?AppendWriteBlockToFlushQueue@CClfsMarshallingContext@@AEAAKEKPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong,_OVERLAPPED *)
0x18001191e  mov     rcx, rsi; CriticalSection
0x180011921  call    cs:__imp_RtlLeaveCriticalSection
0x180011928  nop     dword ptr [rax+rax+00h]
0x18001192d  xor     r9d, r9d; struct _OVERLAPPED *
0x180011930  lea     r8, [rsp+28h+arg_0]; union _CLS_LSN *
0x180011935  lea     rdx, [rsp+28h+arg_8]; union _CLS_LSN *
0x18001193a  mov     rcx, rbx; this
0x18001193d  call    ?FlushToLsn@CClfsMarshallingContext@@QEAAKAEBT_CLS_LSN@@AEAT2@PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::FlushToLsn(_CLS_LSN const &,_CLS_LSN &,_OVERLAPPED *)
0x180011942  mov     rbx, [rsp+28h+arg_10]
0x180011947  xor     eax, eax
0x180011949  mov     rsi, [rsp+28h+arg_18]
0x18001194e  add     rsp, 20h
0x180011952  pop     rdi
0x180011953  retn
```
