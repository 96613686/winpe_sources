# AhgGenomeGetManifest

- ea: `0x180009fe8`
- end: `0x18000a1ff`
- name: `AhgGenomeGetManifest`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180009cdc`

## callees

- `0x180009fe8`
- `0x18000a8f0`
- `0x18000ae60`
- `0x18000b048`
- `0x18000e240`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x18000a1eb`
- `KERNEL32!ReleaseActCtx` at `0x18000a1eb`
- `KERNEL32!CreateActCtxW` at `0x18000a03d`
- `KERNEL32!CreateActCtxW` at `0x18000a058`
- `KERNEL32!CreateActCtxW` at `0x18000a03d`
- `KERNEL32!CreateActCtxW` at `0x18000a058`
- `KERNEL32!GetLastError` at `0x18000a067`
- `KERNEL32!GetLastError` at `0x18000a067`
- `ntdll!RtlFreeHeap` at `0x18000a187`
- `ntdll!RtlFreeHeap` at `0x18000a187`

## string_xrefs

- `0x18000a06d`: `Failed to create activation context [%d]`
- `0x18000a07a`: `AhgGenomeGetManifest`
- `0x18000a0b5`: `AhgGenomeGetManifest`
- `0x18000a13a`: `AhgGenomeGetManifest`
- `0x18000a1cf`: `AhgGenomeGetManifest`
- `0x18000a0a4`: `Failed to get supported OS from application manifest [%d]`
- `0x18000a128`: `Failed to set data for attribute AHG_TAG_MANIFEST_SUPPORTED_OS`
- `0x18000a1c2`: `No UAC manifest`
- `0x18000a14e`: `Failed to read run level information [%d]`
- `0x18000a15f`: `AhgManifestReadRunLevel`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetManifest(const WCHAR *a1)
{
  HANDLE v2; // rdi
  DWORD LastError; // ebx
  int v4; // eax
  int v5; // eax
  PVOID v6; // rbx
  int v7; // r14d
  const char *v8; // r9
  __int64 v9; // r8
  ACTCTXW pActCtx; // [rsp+30h] [rbp-40h] BYREF
  int v12; // [rsp+A0h] [rbp+30h] BYREF
  PVOID P; // [rsp+A8h] [rbp+38h] BYREF
  int v14; // [rsp+B0h] [rbp+40h] BYREF

  pActCtx.lpSource = a1;
  LODWORD(P) = 0;
  v12 = 0;
  v14 = 0;
  *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
  pActCtx.cbSize = 56;
  *(_OWORD *)&pActCtx.lpApplicationName = 0;
  pActCtx.lpResourceName = (LPCWSTR)1;
  pActCtx.dwFlags = 8;
  v2 = CreateActCtxW(&pActCtx);
  if ( v2 != (HANDLE)-1LL || (pActCtx.lpResourceName = (LPCWSTR)2, v2 = CreateActCtxW(&pActCtx), v2 != (HANDLE)-1LL) )
  {
    v4 = AhgManifestReadSupportedOs(&P, v2);
    if ( v4 )
    {
      AslLogCallPrintf(3, "AhgGenomeGetManifest", 654, "Failed to get supported OS from application manifest [%d]", v4);
    }
    else
    {
      v14 = WORD1(P) + ((unsigned __int16)P << 16);
      if ( !(unsigned int)AhgpSetAttribute(a1 + 388, 16, &v14) )
      {
        v8 = "Failed to set data for attribute AHG_TAG_MANIFEST_SUPPORTED_OS";
        v9 = 664;
LABEL_11:
        LastError = 87;
        AslLogCallPrintf(1, "AhgGenomeGetManifest", v9, v8);
LABEL_21:
        ReleaseActCtx(v2);
        return LastError;
      }
    }
    v12 = 0;
    P = 0;
    v5 = AhgpManifestRead(&P, v2, 5);
    v6 = P;
    v7 = v5;
    if ( v5 || !P )
      AslLogCallPrintf(3, "AhgManifestReadRunLevel", 286, "Failed to read run level information [%d]", v5);
    else
      v12 = *((_DWORD *)P + 1);
    if ( v6 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    if ( v7 || !v12 )
    {
      AslLogCallPrintf(3, "AhgGenomeGetManifest", 672, "No UAC manifest");
    }
    else if ( !(unsigned int)AhgpSetAttribute(a1 + 396, 17, &v12) )
    {
      v8 = "Failed to set data for attribute AHG_TAG_UAC_RUN_LEVEL";
      v9 = 680;
      goto LABEL_11;
    }
    LastError = 0;
    goto LABEL_21;
  }
  LastError = GetLastError();
  AslLogCallPrintf(2, "AhgGenomeGetManifest", 648, "Failed to create activation context [%d]", LastError);
  return LastError;
}

```

## disassembly

```asm
0x180009fe8  push    rbp
0x180009fea  push    rbx
0x180009feb  push    rdi
0x180009fec  push    r14
0x180009fee  push    r15
0x180009ff0  mov     rbp, rsp
0x180009ff3  sub     rsp, 70h
0x180009ff7  mov     r15, rcx
0x180009ffa  mov     [rbp+pActCtx.lpSource], rcx
0x180009ffe  xorps   xmm0, xmm0
0x18000a001  mov     dword ptr [rbp+P], 0
0x18000a008  xorps   xmm1, xmm1
0x18000a00b  mov     [rbp+arg_0], 0
0x18000a012  lea     rcx, [rbp+pActCtx]; pActCtx
0x18000a016  mov     [rbp+arg_10], 0
0x18000a01d  movdqu  xmmword ptr [rbp+pActCtx.wProcessorArchitecture], xmm0
0x18000a022  mov     [rbp+pActCtx.cbSize], 38h ; '8'
0x18000a029  movdqu  xmmword ptr [rbp+pActCtx.lpApplicationName], xmm1
0x18000a02e  mov     [rbp+pActCtx.lpResourceName], 1
0x18000a036  mov     [rbp+pActCtx.dwFlags], 8
0x18000a03d  call    cs:__imp_CreateActCtxW
0x18000a043  mov     rdi, rax
0x18000a046  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a04a  jnz     short loc_18000A094
0x18000a04c  lea     r14d, [rax+3]
0x18000a050  lea     rcx, [rbp+pActCtx]; pActCtx
0x18000a054  mov     [rbp+pActCtx.lpResourceName], r14
0x18000a058  call    cs:__imp_CreateActCtxW
0x18000a05e  mov     rdi, rax
0x18000a061  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a065  jnz     short loc_18000A094
0x18000a067  call    cs:__imp_GetLastError
0x18000a06d  lea     r9, aFailedToCreate; "Failed to create activation context [%d"...
0x18000a074  mov     r8d, 288h
0x18000a07a  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x18000a081  mov     [rsp+70h+var_50], eax
0x18000a085  mov     ecx, r14d
0x18000a088  mov     ebx, eax
0x18000a08a  call    AslLogCallPrintf
0x18000a08f  jmp     loc_18000A1F1
0x18000a094  mov     rdx, rdi
0x18000a097  lea     rcx, [rbp+P]
0x18000a09b  call    AhgManifestReadSupportedOs
0x18000a0a0  test    eax, eax
0x18000a0a2  jz      short loc_18000A0FF
0x18000a0a4  lea     r9, aFailedToGetSup; "Failed to get supported OS from applica"...
0x18000a0ab  mov     [rsp+70h+var_50], eax
0x18000a0af  mov     r8d, 28Eh
0x18000a0b5  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x18000a0bc  mov     ecx, 3
0x18000a0c1  call    AslLogCallPrintf
0x18000a0c6  mov     r8d, 5
0x18000a0cc  mov     [rbp+arg_0], 0
0x18000a0d3  mov     rdx, rdi
0x18000a0d6  mov     [rbp+P], 0
0x18000a0de  lea     rcx, [rbp+P]
0x18000a0e2  call    AhgpManifestRead
0x18000a0e7  mov     rbx, [rbp+P]
0x18000a0eb  mov     r14d, eax
0x18000a0ee  test    eax, eax
0x18000a0f0  jnz     short loc_18000A14E
0x18000a0f2  test    rbx, rbx
0x18000a0f5  jz      short loc_18000A14E
0x18000a0f7  mov     eax, [rbx+4]
0x18000a0fa  mov     [rbp+arg_0], eax
0x18000a0fd  jmp     short loc_18000A170
0x18000a0ff  movzx   eax, word ptr [rbp+P+2]
0x18000a103  lea     rcx, [r15+308h]
0x18000a10a  movzx   edx, word ptr [rbp+P]
0x18000a10e  lea     r8, [rbp+arg_10]
0x18000a112  shl     edx, 10h
0x18000a115  add     edx, eax
0x18000a117  mov     [rbp+arg_10], edx
0x18000a11a  mov     edx, 10h
0x18000a11f  call    AhgpSetAttribute
0x18000a124  test    eax, eax
0x18000a126  jnz     short loc_18000A0C6
0x18000a128  lea     r9, aFailedToSetDat; "Failed to set data for attribute AHG_TA"...
0x18000a12f  mov     r8d, 298h
0x18000a135  mov     ebx, 57h ; 'W'
0x18000a13a  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x18000a141  lea     ecx, [rbx-56h]
0x18000a144  call    AslLogCallPrintf
0x18000a149  jmp     loc_18000A1E2
0x18000a14e  lea     r9, aFailedToReadRu; "Failed to read run level information [%"...
0x18000a155  mov     [rsp+70h+var_50], eax
0x18000a159  mov     r8d, 11Eh
0x18000a15f  lea     rdx, aAhgmanifestrea_0; "AhgManifestReadRunLevel"
0x18000a166  mov     ecx, 3
0x18000a16b  call    AslLogCallPrintf
0x18000a170  test    rbx, rbx
0x18000a173  jz      short loc_18000A18D
0x18000a175  mov     rcx, gs:60h
0x18000a17e  mov     r8, rbx; P
0x18000a181  xor     edx, edx; Flags
0x18000a183  mov     rcx, [rcx+30h]; HeapHandle
0x18000a187  call    cs:__imp_RtlFreeHeap
0x18000a18d  test    r14d, r14d
0x18000a190  jnz     short loc_18000A1C2
0x18000a192  cmp     [rbp+arg_0], r14d
0x18000a196  jz      short loc_18000A1C2
0x18000a198  lea     edx, [r14+11h]
0x18000a19c  lea     rcx, [r15+318h]
0x18000a1a3  lea     r8, [rbp+arg_0]
0x18000a1a7  call    AhgpSetAttribute
0x18000a1ac  test    eax, eax
0x18000a1ae  jnz     short loc_18000A1E0
0x18000a1b0  lea     r9, aFailedToSetDat_0; "Failed to set data for attribute AHG_TA"...
0x18000a1b7  mov     r8d, 2A8h
0x18000a1bd  jmp     loc_18000A135
0x18000a1c2  lea     r9, aNoUacManifest; "No UAC manifest"
0x18000a1c9  mov     r8d, 2A0h
0x18000a1cf  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x18000a1d6  mov     ecx, 3
0x18000a1db  call    AslLogCallPrintf
0x18000a1e0  xor     ebx, ebx
0x18000a1e2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000a1e6  jz      short loc_18000A1F1
0x18000a1e8  mov     rcx, rdi; hActCtx
0x18000a1eb  call    cs:__imp_ReleaseActCtx
0x18000a1f1  mov     eax, ebx
0x18000a1f3  add     rsp, 70h
0x18000a1f7  pop     r15
0x18000a1f9  pop     r14
0x18000a1fb  pop     rdi
0x18000a1fc  pop     rbx
0x18000a1fd  pop     rbp
0x18000a1fe  retn
```
