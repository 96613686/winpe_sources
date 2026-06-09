# DeleteFilterInterface

- ea: `0x180013fe0`
- end: `0x180014192`
- name: `DeleteFilterInterface`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014740`
- `0x180016734`

## callees

- `0x180011790`
- `0x180013fe0`
- `0x180053d48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001409d`
- `KERNEL32!HeapFree` at `0x1800140bd`
- `KERNEL32!HeapFree` at `0x18001409d`
- `KERNEL32!HeapFree` at `0x1800140bd`

## string_xrefs

- `0x18001405a`: `Entered: DeleteFilterInterface`
- `0x1800140e6`: `DeleteFilterInterface: No context, assuming interface %ws not added to filter driver`
- `0x18001412b`: `Leaving: DeleteFilterInterface`

## pseudocode

```c
__int64 __fastcall DeleteFilterInterface(__int64 *a1)
{
  InterfaceContainer *v2; // rcx
  __int128 *v3; // r9
  void *v4; // r8
  void *v5; // r8
  void *v6; // rdx
  __int64 v7; // r8
  const wchar_t *v8; // r8
  __int128 *v9; // r9
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+4Ch] [rbp-B4h]
  __int128 v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+6Ch] [rbp-94h]
  int v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v11 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v12) = 0;
    v3 = &v11;
    if ( a1 != (__int64 *)-688LL )
      LODWORD(v3) = (_DWORD)a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: DeleteFilterInterface",
      (_DWORD)v3,
      a1[9],
      (__int64)&v12);
  }
  v4 = (void *)a1[14];
  if ( v4 )
  {
    HeapFree(IPRouterHeap, 0, v4);
    a1[14] = 0;
  }
  v5 = (void *)a1[15];
  if ( v5 )
  {
    HeapFree(IPRouterHeap, 0, v5);
    a1[15] = 0;
  }
  v6 = (void *)a1[12];
  if ( v6 == (void *)-1LL )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 0;
    v7 = a1[9];
    LOWORD(v16) = 0;
    LOWORD(v12) = 0;
    FormatRRASErrorString(
      &v16,
      L"DeleteFilterInterface: No context, assuming interface %ws not added to filter driver",
      v7);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 0;
    v8 = (const wchar_t *)&v16;
  }
  else
  {
    InterfaceContainer::DeleteInterface(v2, v6);
    a1[12] = -1;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 0;
    v8 = L"Leaving: DeleteFilterInterface";
    LOWORD(v12) = 0;
  }
  v9 = &v11;
  if ( a1 != (__int64 *)-688LL )
    LODWORD(v9) = (_DWORD)a1 + 688;
  McTemplateU0zjzz_EventWriteTransfer(
    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
    (unsigned int)RasRtrmgrParamTraceInfo,
    (_DWORD)v8,
    (_DWORD)v9,
    a1[9],
    (__int64)&v12);
  return 0;
}

```

## disassembly

```asm
0x180013fe0  mov     [rsp-8+arg_8], rbx
0x180013fe5  push    rbp
0x180013fe6  lea     rbp, [rsp-780h]
0x180013fee  sub     rsp, 880h
0x180013ff5  mov     rax, cs:__security_cookie
0x180013ffc  xor     rax, rsp
0x180013fff  mov     [rbp+780h+var_10], rax
0x180014006  mov     rbx, rcx
0x180014009  xor     eax, eax
0x18001400b  lea     rcx, [rsp+880h+var_80C]; void *
0x180014010  mov     [rsp+880h+var_810], eax
0x180014014  xor     edx, edx; Val
0x180014016  mov     r8d, 7FCh; Size
0x18001401c  call    memset_0
0x180014021  xor     eax, eax
0x180014023  xorps   xmm0, xmm0
0x180014026  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001402d  mov     [rsp+880h+var_838], eax
0x180014031  movups  [rsp+880h+var_834], xmm0
0x180014036  mov     [rsp+880h+var_814], eax
0x18001403a  movups  [rsp+880h+var_824], xmm0
0x18001403f  movups  [rsp+880h+var_848], xmm0
0x180014044  jz      short loc_18001408B
0x180014046  mov     word ptr [rsp+880h+var_838], ax
0x18001404b  lea     r9, [rsp+880h+var_848]
0x180014050  lea     rax, [rbx+2B0h]
0x180014057  test    rax, rax
0x18001405a  lea     r8, aEnteredDeletef; "Entered: DeleteFilterInterface"
0x180014061  lea     rdx, RasRtrmgrParamTraceInfo
0x180014068  cmovnz  r9, rax
0x18001406c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014073  lea     rax, [rsp+880h+var_838]
0x180014078  mov     [rsp+880h+var_858], rax
0x18001407d  mov     rax, [rbx+48h]
0x180014081  mov     [rsp+880h+var_860], rax
0x180014086  call    McTemplateU0zjzz_EventWriteTransfer
0x18001408b  mov     r8, [rbx+70h]; lpMem
0x18001408f  test    r8, r8
0x180014092  jz      short loc_1800140AB
0x180014094  mov     rcx, cs:IPRouterHeap; hHeap
0x18001409b  xor     edx, edx; dwFlags
0x18001409d  call    cs:__imp_HeapFree
0x1800140a3  mov     qword ptr [rbx+70h], 0
0x1800140ab  mov     r8, [rbx+78h]; lpMem
0x1800140af  test    r8, r8
0x1800140b2  jz      short loc_1800140CB
0x1800140b4  mov     rcx, cs:IPRouterHeap; hHeap
0x1800140bb  xor     edx, edx; dwFlags
0x1800140bd  call    cs:__imp_HeapFree
0x1800140c3  mov     qword ptr [rbx+78h], 0
0x1800140cb  mov     rdx, [rbx+60h]; void *
0x1800140cf  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800140d3  jnz     short loc_180014113
0x1800140d5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800140dc  jge     loc_180014170
0x1800140e2  mov     r8, [rbx+48h]
0x1800140e6  lea     rdx, aDeletefilterin; "DeleteFilterInterface: No context, assu"...
0x1800140ed  xor     eax, eax
0x1800140ef  lea     rcx, [rsp+880h+var_810]
0x1800140f4  mov     word ptr [rsp+880h+var_810], ax
0x1800140f9  mov     word ptr [rsp+880h+var_838], ax
0x1800140fe  call    FormatRRASErrorString
0x180014103  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001410a  jge     short loc_180014170
0x18001410c  lea     r8, [rsp+880h+var_810]
0x180014111  jmp     short loc_180014137
0x180014113  call    ?DeleteInterface@InterfaceContainer@@QEAAKPEAX@Z; InterfaceContainer::DeleteInterface(void *)
0x180014118  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x180014120  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180014127  jz      short loc_180014170
0x180014129  xor     eax, eax
0x18001412b  lea     r8, aLeavingDeletef; "Leaving: DeleteFilterInterface"
0x180014132  mov     word ptr [rsp+880h+var_838], ax
0x180014137  lea     rax, [rbx+2B0h]
0x18001413e  test    rax, rax
0x180014141  lea     r9, [rsp+880h+var_848]
0x180014146  lea     rdx, RasRtrmgrParamTraceInfo
0x18001414d  cmovnz  r9, rax
0x180014151  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014158  lea     rax, [rsp+880h+var_838]
0x18001415d  mov     [rsp+880h+var_858], rax
0x180014162  mov     rax, [rbx+48h]
0x180014166  mov     [rsp+880h+var_860], rax
0x18001416b  call    McTemplateU0zjzz_EventWriteTransfer
0x180014170  xor     eax, eax
0x180014172  mov     rcx, [rbp+780h+var_10]
0x180014179  xor     rcx, rsp; StackCookie
0x18001417c  call    __security_check_cookie
0x180014181  mov     rbx, [rsp+880h+arg_8]
0x180014189  add     rsp, 880h
0x180014190  pop     rbp
0x180014191  retn
```
