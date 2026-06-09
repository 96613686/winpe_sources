# CClfsMarshallingContext::FreeIocb(CLogIocb *)

- ea: `0x1800101c8`
- end: `0x180010313`
- name: `?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z`
- size: `331`
- prototype: `void __fastcall(CClfsMarshallingContext *__hidden this, struct CLogIocb *)`
- caller_count: `11`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d8c0`
- `0x18000efa0`
- `0x180011854`
- `0x18001195c`
- `0x180012e18`
- `0x1800130a0`
- `0x180013178`
- `0x1800136a0`
- `0x180013cc0`
- `0x180014008`
- `0x180014328`

## callees

- `0x1800101c8`
- `0x18001031c`
- `0x180013058`
- `0x180014bdc`
- `0x180016010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800102f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18001593c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800102f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18001593c`
- `ntdll!RtlEnterCriticalSection` at `0x1800101ef`
- `ntdll!RtlEnterCriticalSection` at `0x1800101ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001026f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001026f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001025f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001025f`

## pseudocode

```c
void __fastcall CClfsMarshallingContext::FreeIocb(CClfsMarshallingContext *this, struct CLogIocb *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // rax
  char v6; // si
  void *v7; // r8
  void (__fastcall *v8)(_QWORD, _QWORD); // rax
  int v9; // r8d

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  v5 = 116;
  if ( *((_DWORD *)a2 + 4) != -1040322544 )
    v5 = 112;
  v6 = _InterlockedDecrement((volatile signed __int32 *)((char *)this + v5));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 6, 0xFFFFFFFF) == 1 )
  {
    v7 = (void *)*((_QWORD *)a2 + 8);
    if ( v7 )
    {
      v8 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)a2 + 26);
      if ( v8 )
      {
        v8(*((_QWORD *)a2 + 8), *((_QWORD *)a2 + 27));
      }
      else if ( !HeapFree(g_hMarshalHeap, 0, v7) )
      {
        GetLastError();
LABEL_10:
        CClfsMarshallingContext::Release(*((CClfsMarshallingContext **)a2 + 24));
        goto LABEL_11;
      }
      *((_QWORD *)a2 + 8) = 0;
      goto LABEL_10;
    }
  }
LABEL_11:
  CClfsMarshallingContext::FreeIocbNaked(this, a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
    WPP_SF_slqqdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      v9,
      (unsigned int)"CClfsMarshallingContext::FreeIocb",
      193,
      (char)this,
      0,
      v6,
      *((_DWORD *)this + 35));
  RtlLeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x1800101c8  mov     [rsp+arg_8], rbx
0x1800101cd  mov     [rsp+arg_0], rcx
0x1800101d2  push    rsi
0x1800101d3  push    rdi
0x1800101d4  push    r14
0x1800101d6  sub     rsp, 60h
0x1800101da  mov     rbx, rdx
0x1800101dd  mov     rdi, rcx
0x1800101e0  mov     [rsp+78h+var_28], 0
0x1800101e5  lea     r14, [rcx+120h]
0x1800101ec  mov     rcx, r14; CriticalSection
0x1800101ef  call    cs:__imp_RtlEnterCriticalSection
0x1800101f6  nop     dword ptr [rax+rax+00h]
0x1800101fb  mov     [rsp+78h+var_28], 1
0x180010200  mov     eax, 74h ; 't'
0x180010205  lea     ecx, [rax-4]
0x180010208  cmp     dword ptr [rbx+10h], 0C1FDF010h
0x18001020f  cmovnz  eax, ecx
0x180010212  or      ecx, 0FFFFFFFFh
0x180010215  mov     esi, ecx
0x180010217  lock xadd [rax+rdi], esi
0x18001021c  add     esi, ecx
0x18001021e  mov     eax, ecx
0x180010220  lock xadd [rbx+18h], eax
0x180010225  add     eax, ecx
0x180010227  mov     [rsp+78h+arg_10], eax
0x18001022e  jnz     short loc_180010291
0x180010230  mov     r8, [rbx+40h]; lpMem
0x180010234  test    r8, r8
0x180010237  jz      short loc_180010291
0x180010239  mov     rax, [rbx+0D0h]
0x180010240  test    rax, rax
0x180010243  jz      short loc_180010256
0x180010245  mov     rdx, [rbx+0D8h]
0x18001024c  mov     rcx, r8
0x18001024f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010254  jmp     short loc_18001027D
0x180010256  xor     edx, edx; dwFlags
0x180010258  mov     rcx, cs:?g_hMarshalHeap@@3PEAXEA; hHeap
0x18001025f  call    cs:__imp_HeapFree
0x180010266  nop     dword ptr [rax+rax+00h]
0x18001026b  test    eax, eax
0x18001026d  jnz     short loc_18001027D
0x18001026f  call    cs:__imp_GetLastError
0x180010276  nop     dword ptr [rax+rax+00h]
0x18001027b  jmp     short loc_180010285
0x18001027d  mov     qword ptr [rbx+40h], 0
0x180010285  mov     rcx, [rbx+0C0h]; this
0x18001028c  call    ?Release@CClfsMarshallingContext@@QEAAKXZ; CClfsMarshallingContext::Release(void)
0x180010291  mov     rdx, rbx; struct CLogIocb *
0x180010294  mov     rcx, rdi; this
0x180010297  call    ?FreeIocbNaked@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocbNaked(CLogIocb *)
0x18001029c  lea     rax, WPP_GLOBAL_Control
0x1800102a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102aa  cmp     rcx, rax
0x1800102ad  jz      short loc_1800102F2
0x1800102af  test    dword ptr [rcx+1Ch], 4000000h
0x1800102b6  jz      short loc_1800102F2
0x1800102b8  mov     edx, 0Ch
0x1800102bd  mov     eax, [rdi+8Ch]
0x1800102c3  mov     [rsp+78h+var_38], eax
0x1800102c7  mov     [rsp+78h+var_40], esi
0x1800102cb  mov     [rsp+78h+var_48], 0
0x1800102d4  mov     [rsp+78h+var_50], rdi
0x1800102d9  mov     [rsp+78h+var_58], 15C1h
0x1800102e1  lea     r9, aCclfsmarshalli_1; "CClfsMarshallingContext::FreeIocb"
0x1800102e8  mov     rcx, [rcx+10h]
0x1800102ec  call    WPP_SF_slqqdd
0x1800102f1  nop
0x1800102f2  mov     rcx, r14; CriticalSection
0x1800102f5  call    cs:__imp_RtlLeaveCriticalSection
0x1800102fc  nop     dword ptr [rax+rax+00h]
0x180010301  mov     rbx, [rsp+78h+arg_8]
0x180010309  add     rsp, 60h
0x18001030d  pop     r14
0x18001030f  pop     rdi
0x180010310  pop     rsi
0x180010311  retn
0x18001591f  push    rbp
0x180015921  sub     rsp, 50h
0x180015925  mov     rbp, rdx
0x180015928  cmp     byte ptr [rbp+50h], 0
0x18001592c  jz      short loc_18001594C
0x18001592e  mov     rcx, [rbp+80h]
0x180015935  add     rcx, 120h; CriticalSection
0x18001593c  call    cs:__imp_RtlLeaveCriticalSection
0x180015943  nop     dword ptr [rax+rax+00h]
0x180015948  mov     byte ptr [rbp+50h], 0
0x18001594c  add     rsp, 50h
0x180015950  pop     rbp
0x180015951  retn
```
