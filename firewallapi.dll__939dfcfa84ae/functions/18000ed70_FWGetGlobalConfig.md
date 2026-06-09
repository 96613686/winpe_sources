# FWGetGlobalConfig

- ea: `0x18000ed70`
- end: `0x18000eef8`
- name: `FWGetGlobalConfig`
- size: `392`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180006270`
- `0x18000bea0`
- `0x18000c810`
- `0x18000d0f0`
- `0x18000f0a0`
- `0x18000fd90`
- `0x18000ffd0`
- `0x1800191e0`
- `0x180021b60`
- `0x180030468`
- `0x1800333a0`
- `0x18003662c`

## callees

- `0x180005e0c`
- `0x18000ed70`
- `0x18000f0a0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000edb4`
- `ntdll!EtwEventWrite` at `0x18000ee4e`
- `ntdll!EtwEventWrite` at `0x18000edb4`
- `ntdll!EtwEventWrite` at `0x18000ee4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000eddd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000eddd`

## pseudocode

```c
__int64 __fastcall FWGetGlobalConfig(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        __int64 a6,
        int *a7)
{
  unsigned int v11; // eax
  unsigned int v12; // ebx
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int64 v17; // rax

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetGlobalConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  if ( a3 == 6 )
    goto LABEL_8;
  if ( !a2 )
    goto LABEL_8;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(a2 + 2 * v17) );
  if ( v17 <= 0xFF )
  {
LABEL_8:
    v11 = Int_FWGetOrSetGlobalConfig(1, a1, a2, a3, 0, a4, a5, a6, a7, 0);
    v12 = v11;
    if ( v11 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 79;
        v16 = v11;
LABEL_15:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v16);
      }
    }
  }
  else
  {
    v12 = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 78;
      v16 = 87;
      goto LABEL_15;
    }
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetGlobalConfig, 0, 0);
  return v12;
}

```

## disassembly

```asm
0x18000ed70  push    rbx
0x18000ed72  push    rbp
0x18000ed73  push    rsi
0x18000ed74  push    rdi
0x18000ed75  push    r12
0x18000ed77  push    r14
0x18000ed79  push    r15
0x18000ed7b  sub     rsp, 50h
0x18000ed7f  mov     r14, [rsp+88h+arg_28]
0x18000ed87  movzx   esi, cx
0x18000ed8a  mov     rcx, cs:g_Provider
0x18000ed91  mov     ebp, r9d
0x18000ed94  mov     r15, [rsp+88h+arg_30]
0x18000ed9c  mov     ebx, r8d
0x18000ed9f  mov     rdi, rdx
0x18000eda2  test    rcx, rcx
0x18000eda5  jz      short loc_18000EDC0
0x18000eda7  xor     r9d, r9d
0x18000edaa  lea     rdx, MPS_CLNT_API_Enter_GetGlobalConfig
0x18000edb1  xor     r8d, r8d
0x18000edb4  call    cs:__imp_EtwEventWrite
0x18000edbb  nop     dword ptr [rax+rax+00h]
0x18000edc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edc7  lea     r12, WPP_GLOBAL_Control
0x18000edce  cmp     rcx, r12
0x18000edd1  jz      short loc_18000EDDD
0x18000edd3  test    byte ptr [rcx+1Ch], 8
0x18000edd7  jnz     loc_18000EE98
0x18000eddd  call    cs:__imp_GetTickCount64
0x18000ede4  nop     dword ptr [rax+rax+00h]
0x18000ede9  cmp     ebx, 6
0x18000edec  jz      short loc_18000EDF7
0x18000edee  test    rdi, rdi
0x18000edf1  jnz     loc_18000EEB2
0x18000edf7  mov     eax, [rsp+88h+arg_20]
0x18000edfe  xor     ecx, ecx
0x18000ee00  mov     [rsp+88h+var_40], rcx
0x18000ee05  mov     r9d, ebx
0x18000ee08  mov     [rsp+88h+var_48], r15
0x18000ee0d  mov     r8, rdi
0x18000ee10  mov     [rsp+88h+var_50], r14
0x18000ee15  movzx   edx, si
0x18000ee18  mov     [rsp+88h+var_58], eax
0x18000ee1c  mov     [rsp+88h+var_60], ebp
0x18000ee20  mov     [rsp+88h+var_68], rcx
0x18000ee25  mov     ecx, 1
0x18000ee2a  call    Int_FWGetOrSetGlobalConfig
0x18000ee2f  mov     ebx, eax
0x18000ee31  test    eax, eax
0x18000ee33  jnz     short loc_18000EE6C
0x18000ee35  mov     rcx, cs:g_Provider
0x18000ee3c  test    rcx, rcx
0x18000ee3f  jz      short loc_18000EE5A
0x18000ee41  xor     r9d, r9d
0x18000ee44  lea     rdx, MPS_CLNT_API_Exit_GetGlobalConfig
0x18000ee4b  xor     r8d, r8d
0x18000ee4e  call    cs:__imp_EtwEventWrite
0x18000ee55  nop     dword ptr [rax+rax+00h]
0x18000ee5a  mov     eax, ebx
0x18000ee5c  add     rsp, 50h
0x18000ee60  pop     r15
0x18000ee62  pop     r14
0x18000ee64  pop     r12
0x18000ee66  pop     rdi
0x18000ee67  pop     rsi
0x18000ee68  pop     rbp
0x18000ee69  pop     rbx
0x18000ee6a  retn
0x18000ee6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee73  cmp     rcx, r12
0x18000ee76  jz      short loc_18000EE35
0x18000ee78  test    byte ptr [rcx+1Ch], 1
0x18000ee7c  jz      short loc_18000EE35
0x18000ee7e  mov     edx, 4Fh ; 'O'
0x18000ee83  mov     r9d, eax
0x18000ee86  mov     rcx, [rcx+10h]
0x18000ee8a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000ee91  call    WPP_SF_d
0x18000ee96  jmp     short loc_18000EE35
0x18000ee98  mov     rcx, [rcx+10h]
0x18000ee9c  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000eea3  mov     edx, 4Dh ; 'M'
0x18000eea8  call    WPP_SF_
0x18000eead  jmp     loc_18000EDDD
0x18000eeb2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000eeb9  inc     rax
0x18000eebc  cmp     word ptr [rdi+rax*2], 0
0x18000eec1  jnz     short loc_18000EEB9
0x18000eec3  cmp     rax, 0FFh
0x18000eec9  jbe     loc_18000EDF7
0x18000eecf  mov     ebx, 57h ; 'W'
0x18000eed4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eedb  cmp     rcx, r12
0x18000eede  jz      loc_18000EE35
0x18000eee4  test    byte ptr [rcx+1Ch], 1
0x18000eee8  jz      loc_18000EE35
0x18000eeee  mov     edx, 4Eh ; 'N'
0x18000eef3  mov     r9d, ebx
0x18000eef6  jmp     short loc_18000EE86
```
