# FWGetGlobalConfig3

- ea: `0x180010990`
- end: `0x180010acc`
- name: `FWGetGlobalConfig3`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180027370`

## callees

- `0x180005e0c`
- `0x18000f0a0`
- `0x180010990`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800109d3`
- `ntdll!EtwEventWrite` at `0x180010a5e`
- `ntdll!EtwEventWrite` at `0x1800109d3`
- `ntdll!EtwEventWrite` at `0x180010a5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800109f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800109f6`

## pseudocode

```c
__int64 __fastcall FWGetGlobalConfig3(__int64 a1, int a2, int a3, __int64 a4, int *a5, _DWORD *a6)
{
  unsigned int v10; // r9d
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetGlobalConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v10 = *(_DWORD *)(a1 + 16);
  v11 = a1;
  if ( v10 != 6 )
    v11 = 0;
  v12 = Int_FWGetOrSetGlobalConfig(1, *(_WORD *)(a1 + 2), *(_QWORD *)(a1 + 8), v10, v11, a2, a3, a4, a5, a6);
  v13 = v12;
  if ( v12 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v12);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetGlobalConfig, 0, 0);
  return v13;
}

```

## disassembly

```asm
0x180010990  push    rbx
0x180010992  push    rbp
0x180010993  push    rsi
0x180010994  push    rdi
0x180010995  push    r12
0x180010997  push    r14
0x180010999  push    r15
0x18001099b  sub     rsp, 50h
0x18001099f  mov     r14, [rsp+88h+arg_20]
0x1800109a7  mov     rbx, rcx
0x1800109aa  mov     rcx, cs:g_Provider
0x1800109b1  mov     rbp, r9
0x1800109b4  mov     r15, [rsp+88h+arg_28]
0x1800109bc  mov     esi, r8d
0x1800109bf  mov     edi, edx
0x1800109c1  test    rcx, rcx
0x1800109c4  jz      short loc_1800109DF
0x1800109c6  xor     r9d, r9d
0x1800109c9  lea     rdx, MPS_CLNT_API_Enter_GetGlobalConfig
0x1800109d0  xor     r8d, r8d
0x1800109d3  call    cs:__imp_EtwEventWrite
0x1800109da  nop     dword ptr [rax+rax+00h]
0x1800109df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109e6  lea     r12, WPP_GLOBAL_Control
0x1800109ed  cmp     rcx, r12
0x1800109f0  jnz     loc_180010AA8
0x1800109f6  call    cs:__imp_GetTickCount64
0x1800109fd  nop     dword ptr [rax+rax+00h]
0x180010a02  mov     r9d, [rbx+10h]
0x180010a06  xor     eax, eax
0x180010a08  mov     r8, [rbx+8]
0x180010a0c  cmp     r9d, 6
0x180010a10  movzx   edx, word ptr [rbx+2]
0x180010a14  mov     rcx, rbx
0x180010a17  mov     [rsp+88h+var_40], r15
0x180010a1c  cmovnz  rcx, rax
0x180010a20  mov     [rsp+88h+var_48], r14
0x180010a25  mov     [rsp+88h+var_50], rbp
0x180010a2a  mov     [rsp+88h+var_58], esi
0x180010a2e  mov     [rsp+88h+var_60], edi
0x180010a32  mov     [rsp+88h+var_68], rcx
0x180010a37  lea     ecx, [rax+1]
0x180010a3a  call    Int_FWGetOrSetGlobalConfig
0x180010a3f  mov     ebx, eax
0x180010a41  test    eax, eax
0x180010a43  jnz     short loc_180010A7C
0x180010a45  mov     rcx, cs:g_Provider
0x180010a4c  test    rcx, rcx
0x180010a4f  jz      short loc_180010A6A
0x180010a51  xor     r9d, r9d
0x180010a54  lea     rdx, MPS_CLNT_API_Exit_GetGlobalConfig
0x180010a5b  xor     r8d, r8d
0x180010a5e  call    cs:__imp_EtwEventWrite
0x180010a65  nop     dword ptr [rax+rax+00h]
0x180010a6a  mov     eax, ebx
0x180010a6c  add     rsp, 50h
0x180010a70  pop     r15
0x180010a72  pop     r14
0x180010a74  pop     r12
0x180010a76  pop     rdi
0x180010a77  pop     rsi
0x180010a78  pop     rbp
0x180010a79  pop     rbx
0x180010a7a  retn
0x180010a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a83  cmp     rcx, r12
0x180010a86  jz      short loc_180010A45
0x180010a88  test    byte ptr [rcx+1Ch], 1
0x180010a8c  jz      short loc_180010A45
0x180010a8e  mov     rcx, [rcx+10h]
0x180010a92  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180010a99  mov     edx, 51h ; 'Q'
0x180010a9e  mov     r9d, ebx
0x180010aa1  call    WPP_SF_d
0x180010aa6  jmp     short loc_180010A45
0x180010aa8  test    byte ptr [rcx+1Ch], 8
0x180010aac  jz      loc_1800109F6
0x180010ab2  mov     rcx, [rcx+10h]
0x180010ab6  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180010abd  mov     edx, 50h ; 'P'
0x180010ac2  call    WPP_SF_
0x180010ac7  jmp     loc_1800109F6
```
