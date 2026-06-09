# DeleteInterfaceFromAllProtocols

- ea: `0x180016560`
- end: `0x18001672c`
- name: `DeleteInterfaceFromAllProtocols`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016734`

## callees

- `0x180011790`
- `0x180016560`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180016709`
- `ntdll!RtlReleaseResource` at `0x180016709`
- `ntdll!RtlAcquireResourceShared` at `0x180016620`
- `ntdll!RtlAcquireResourceShared` at `0x180016620`
- `KERNEL32!HeapFree` at `0x1800166f0`
- `KERNEL32!HeapFree` at `0x1800166f0`

## string_xrefs

- `0x1800165d9`: `DeleteInterfaceFromAllProtocols`
- `0x180016677`: `DeleteInterfaceFromAllProtocols : memory freed for  interface %ws of type  %d at %X`

## pseudocode

```c
__int64 __fastcall DeleteInterfaceFromAllProtocols(__int64 a1)
{
  __int128 *v2; // r9
  _QWORD **v3; // rdi
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  __int128 *v8; // r9
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+4Ch] [rbp-B4h]
  __int128 v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+6Ch] [rbp-94h]
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v10 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v11) = 0;
    v2 = &v10;
    if ( a1 != -688 )
      LODWORD(v2) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"DeleteInterfaceFromAllProtocols",
      (_DWORD)v2,
      *(_QWORD *)(a1 + 72),
      (__int64)&v11);
  }
  if ( (_DWORD)RouterState != 2 )
  {
    RtlAcquireResourceShared(&stru_18008C4A0, 1u);
    v3 = (_QWORD **)(a1 + 56);
    while ( 1 )
    {
      v4 = *v3;
      if ( *v3 == v3 )
        break;
      if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
        __fastfail(3u);
      *v3 = v5;
      v5[1] = v3;
      (*(void (__fastcall **)(_QWORD))(v4[3] + 136LL))(*(unsigned int *)(a1 + 16));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v6 = *(unsigned int *)(a1 + 516);
        v7 = *(_QWORD *)(a1 + 72);
        LOWORD(v15) = 0;
        LOWORD(v11) = 0;
        FormatRRASErrorString(
          &v15,
          L"DeleteInterfaceFromAllProtocols : memory freed for  interface %ws of type  %d at %X",
          v7,
          v6,
          v4);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v8 = &v10;
          if ( a1 != -688 )
            LODWORD(v8) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v15,
            (_DWORD)v8,
            *(_QWORD *)(a1 + 72),
            (__int64)&v11);
        }
      }
      HeapFree(IPRouterHeap, 0, v4);
    }
    RtlReleaseResource(&stru_18008C4A0);
  }
  return 0;
}

```

## disassembly

```asm
0x180016560  push    rbp
0x180016562  push    rbx
0x180016563  push    rsi
0x180016564  push    rdi
0x180016565  lea     rbp, [rsp-788h]
0x18001656d  sub     rsp, 888h
0x180016574  mov     rax, cs:__security_cookie
0x18001657b  xor     rax, rsp
0x18001657e  mov     [rbp+7A0h+var_30], rax
0x180016585  mov     rsi, rcx
0x180016588  xor     eax, eax
0x18001658a  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18001658f  mov     [rsp+8A0h+var_830], eax
0x180016593  xor     edx, edx; Val
0x180016595  mov     r8d, 7FCh; Size
0x18001659b  call    memset_0
0x1800165a0  xor     eax, eax
0x1800165a2  xorps   xmm0, xmm0
0x1800165a5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800165ac  mov     [rsp+8A0h+var_858], eax
0x1800165b0  movups  [rsp+8A0h+var_854], xmm0
0x1800165b5  mov     [rsp+8A0h+var_834], eax
0x1800165b9  movups  [rsp+8A0h+var_844], xmm0
0x1800165be  movups  [rsp+8A0h+var_868], xmm0
0x1800165c3  jz      short loc_18001660A
0x1800165c5  mov     word ptr [rsp+8A0h+var_858], ax
0x1800165ca  lea     r9, [rsp+8A0h+var_868]
0x1800165cf  lea     rax, [rsi+2B0h]
0x1800165d6  test    rax, rax
0x1800165d9  lea     r8, aDeleteinterfac_2; "DeleteInterfaceFromAllProtocols"
0x1800165e0  lea     rdx, RasRtrmgrParamTraceInfo
0x1800165e7  cmovnz  r9, rax
0x1800165eb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800165f2  lea     rax, [rsp+8A0h+var_858]
0x1800165f7  mov     [rsp+8A0h+var_878], rax
0x1800165fc  mov     rax, [rsi+48h]
0x180016600  mov     [rsp+8A0h+var_880], rax
0x180016605  call    McTemplateU0zjzz_EventWriteTransfer
0x18001660a  cmp     dword ptr cs:RouterState, 2
0x180016611  jz      loc_18001670F
0x180016617  mov     dl, 1; Wait
0x180016619  lea     rcx, stru_18008C4A0; Resource
0x180016620  call    cs:__imp_RtlAcquireResourceShared
0x180016626  lea     rdi, [rsi+38h]
0x18001662a  mov     rbx, [rdi]
0x18001662d  cmp     rbx, rdi
0x180016630  jz      loc_180016702
0x180016636  cmp     [rbx+8], rdi
0x18001663a  jnz     loc_1800166FB
0x180016640  mov     rax, [rbx]
0x180016643  cmp     [rax+8], rbx
0x180016647  jnz     loc_1800166FB
0x18001664d  mov     [rdi], rax
0x180016650  mov     [rax+8], rdi
0x180016654  mov     rax, [rbx+18h]
0x180016658  mov     ecx, [rsi+10h]
0x18001665b  mov     rax, [rax+88h]
0x180016662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016667  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001666e  jge     short loc_1800166E4
0x180016670  mov     r9d, [rsi+204h]
0x180016677  lea     rdx, aDeleteinterfac_0; "DeleteInterfaceFromAllProtocols : memor"...
0x18001667e  mov     r8, [rsi+48h]
0x180016682  lea     rcx, [rsp+8A0h+var_830]
0x180016687  xor     eax, eax
0x180016689  mov     [rsp+8A0h+var_880], rbx
0x18001668e  mov     word ptr [rsp+8A0h+var_830], ax
0x180016693  mov     word ptr [rsp+8A0h+var_858], ax
0x180016698  call    FormatRRASErrorString
0x18001669d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800166a4  jge     short loc_1800166E4
0x1800166a6  lea     rax, [rsi+2B0h]
0x1800166ad  test    rax, rax
0x1800166b0  lea     r9, [rsp+8A0h+var_868]
0x1800166b5  lea     r8, [rsp+8A0h+var_830]
0x1800166ba  cmovnz  r9, rax
0x1800166be  lea     rdx, RasRtrmgrParamTraceInfo
0x1800166c5  lea     rax, [rsp+8A0h+var_858]
0x1800166ca  mov     [rsp+8A0h+var_878], rax
0x1800166cf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800166d6  mov     rax, [rsi+48h]
0x1800166da  mov     [rsp+8A0h+var_880], rax
0x1800166df  call    McTemplateU0zjzz_EventWriteTransfer
0x1800166e4  mov     rcx, cs:IPRouterHeap; hHeap
0x1800166eb  mov     r8, rbx; lpMem
0x1800166ee  xor     edx, edx; dwFlags
0x1800166f0  call    cs:__imp_HeapFree
0x1800166f6  jmp     loc_18001662A
0x1800166fb  mov     ecx, 3
0x180016700  int     29h; Win8: RtlFailFast(ecx)
0x180016702  lea     rcx, stru_18008C4A0; Resource
0x180016709  call    cs:__imp_RtlReleaseResource
0x18001670f  xor     eax, eax
0x180016711  mov     rcx, [rbp+7A0h+var_30]
0x180016718  xor     rcx, rsp; StackCookie
0x18001671b  call    __security_check_cookie
0x180016720  add     rsp, 888h
0x180016727  pop     rdi
0x180016728  pop     rsi
0x180016729  pop     rbx
0x18001672a  pop     rbp
0x18001672b  retn
```
