# UpdateCache

- ea: `0x18000baa8`
- end: `0x18000bc03`
- name: `UpdateCache`
- size: `347`
- prototype: ``
- caller_count: `14`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005700`
- `0x180005910`
- `0x180005ba0`
- `0x180005f30`
- `0x180006730`
- `0x180006ad0`
- `0x180006e10`
- `0x180007298`
- `0x1800075ac`
- `0x1800096a0`
- `0x180009b00`
- `0x180009d60`
- `0x18000a0c0`
- `0x180020be4`

## callees

- `0x18000ac60`
- `0x18000ba80`
- `0x18000baa8`
- `0x18002c960`
- `0x18002cc00`
- `0x18002d440`
- `0x18002d540`
- `0x18002def0`
- `0x18002e220`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x18000bb4a`
- `ntdll!RtlConvertSharedToExclusive` at `0x18000bb4a`
- `ntdll!RtlReleaseResource` at `0x18000bbd3`
- `ntdll!RtlReleaseResource` at `0x180058995`
- `ntdll!RtlReleaseResource` at `0x18000bbd3`
- `ntdll!RtlReleaseResource` at `0x180058995`
- `ntdll!RtlAcquireResourceShared` at `0x18000bb09`
- `ntdll!RtlAcquireResourceShared` at `0x18000bb09`
- `KERNEL32!GetTickCount` at `0x18000bb29`
- `KERNEL32!GetTickCount` at `0x18000bbc0`
- `KERNEL32!GetTickCount` at `0x18000bb29`
- `KERNEL32!GetTickCount` at `0x18000bbc0`

## string_xrefs

- `0x18000bb80`: `Error %d loading %hs cache`

## pseudocode

```c
__int64 __fastcall UpdateCache(unsigned int a1, _DWORD *a2)
{
  __int64 v3; // rsi
  int v4; // ebx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v10; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-834h] BYREF

  v3 = a1;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  RtlAcquireResourceShared(&g_LockTable + v3, 1u);
  if ( g_LastUpdateTable[v3] )
  {
    v4 = g_LastUpdateTable[v3];
    if ( GetTickCount() - v4 < g_TimeoutTable[v3] )
    {
      *a2 = 0;
LABEL_10:
      v6 = 0;
      goto LABEL_11;
    }
  }
  RtlConvertSharedToExclusive(&g_LockTable + v3);
  v6 = ((__int64 (__fastcall *)(__int64))g_LoadFunctionTable[v3])(v5);
  if ( !v6 )
  {
    g_LastUpdateTable[v3] = GetTickCount();
    goto LABEL_10;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v10) = 0;
    v7 = CacheToA((unsigned int)v3);
    FormatRRASErrorString(&v10, L"Error %d loading %hs cache", v6, v7, a1);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v10);
  }
  g_LastUpdateTable[v3] = 0;
LABEL_11:
  RtlReleaseResource(&g_LockTable + v3);
  return v6;
}

```

## disassembly

```asm
0x18000baa8  mov     [rsp+arg_10], rbx
0x18000baad  push    rsi
0x18000baae  push    rdi
0x18000baaf  push    r13
0x18000bab1  push    r14
0x18000bab3  push    r15
0x18000bab5  sub     rsp, 840h
0x18000babc  mov     rax, cs:__security_cookie
0x18000bac3  xor     rax, rsp
0x18000bac6  mov     [rsp+868h+var_38], rax
0x18000bace  mov     r15, rdx
0x18000bad1  mov     esi, ecx
0x18000bad3  mov     [rsp+868h+var_848], esi
0x18000bad7  mov     [rsp+868h+var_838], 0
0x18000badf  xor     edx, edx; Val
0x18000bae1  mov     r8d, 7FCh; Size
0x18000bae7  lea     rcx, [rsp+868h+var_834]; void *
0x18000baec  call    memset_0
0x18000baf1  nop
0x18000baf2  lea     r14, [rsi+rsi*2]
0x18000baf6  shl     r14, 5
0x18000bafa  lea     rcx, g_LockTable
0x18000bb01  add     r14, rcx
0x18000bb04  mov     dl, 1; Wait
0x18000bb06  mov     rcx, r14; Resource
0x18000bb09  call    cs:__imp_RtlAcquireResourceShared
0x18000bb0f  lea     r13, cs:180000000h
0x18000bb16  cmp     rva g_LastUpdateTable[r13+rsi*4], 0
0x18000bb1f  jz      short loc_18000BB47
0x18000bb21  mov     ebx, rva g_LastUpdateTable[r13+rsi*4]
0x18000bb29  call    cs:__imp_GetTickCount
0x18000bb2f  sub     eax, ebx
0x18000bb31  cmp     eax, ds:rva g_TimeoutTable[r13+rsi*4]
0x18000bb39  jnb     short loc_18000BB47
0x18000bb3b  mov     dword ptr [r15], 0
0x18000bb42  jmp     loc_18000BBCE
0x18000bb47  mov     rcx, r14; Resource
0x18000bb4a  call    cs:__imp_RtlConvertSharedToExclusive
0x18000bb50  mov     rax, ds:(g_LoadFunctionTable - 180000000h)[r13+rsi*8]
0x18000bb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5d  mov     ebx, eax
0x18000bb5f  test    eax, eax
0x18000bb61  jz      short loc_18000BBC0
0x18000bb63  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000bb6a  jz      short loc_18000BBB2
0x18000bb6c  xor     edx, edx
0x18000bb6e  mov     word ptr [rsp+868h+var_838], dx
0x18000bb73  mov     ecx, esi
0x18000bb75  call    CacheToA
0x18000bb7a  mov     r9, rax
0x18000bb7d  mov     r8d, ebx
0x18000bb80  lea     rdx, aErrorDLoadingH; "Error %d loading %hs cache"
0x18000bb87  lea     rcx, [rsp+868h+var_838]
0x18000bb8c  call    FormatRRASErrorString
0x18000bb91  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000bb98  jz      short loc_18000BBB2
0x18000bb9a  lea     r8, [rsp+868h+var_838]
0x18000bb9f  lea     rdx, RasRtrMgrTraceError
0x18000bba6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bbad  call    McTemplateU0z_EventWriteTransfer
0x18000bbb2  mov     rva g_LastUpdateTable[r13+rsi*4], 0
0x18000bbbe  jmp     short loc_18000BBD0
0x18000bbc0  call    cs:__imp_GetTickCount
0x18000bbc6  mov     rva g_LastUpdateTable[r13+rsi*4], eax
0x18000bbce  xor     ebx, ebx
0x18000bbd0  mov     rcx, r14; Resource
0x18000bbd3  call    cs:__imp_RtlReleaseResource
0x18000bbd9  mov     eax, ebx
0x18000bbdb  mov     rcx, [rsp+868h+var_38]
0x18000bbe3  xor     rcx, rsp; StackCookie
0x18000bbe6  call    __security_check_cookie
0x18000bbeb  mov     rbx, [rsp+868h+arg_10]
0x18000bbf3  add     rsp, 840h
0x18000bbfa  pop     r15
0x18000bbfc  pop     r14
0x18000bbfe  pop     r13
0x18000bc00  pop     rdi
0x18000bc01  pop     rsi
0x18000bc02  retn
0x180058977  push    rbp
0x180058979  sub     rsp, 20h
0x18005897d  mov     rbp, rdx
0x180058980  mov     eax, [rbp+20h]
0x180058983  lea     rcx, [rax+rax*2]
0x180058987  shl     rcx, 5
0x18005898b  lea     rax, g_LockTable
0x180058992  add     rcx, rax; Resource
0x180058995  call    cs:__imp_RtlReleaseResource
0x18005899b  nop
0x18005899c  add     rsp, 20h
0x1800589a0  pop     rbp
0x1800589a1  retn
```
