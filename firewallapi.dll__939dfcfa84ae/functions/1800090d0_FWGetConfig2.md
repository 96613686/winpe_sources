# FWGetConfig2

- ea: `0x1800090d0`
- end: `0x1800091fd`
- name: `FWGetConfig2`
- size: `301`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bea0`
- `0x1800191e0`
- `0x180021b60`
- `0x180027370`
- `0x180030468`
- `0x180033600`
- `0x180033af8`
- `0x1800340d8`
- `0x180035340`
- `0x180039ff0`

## callees

- `0x180005e0c`
- `0x1800090d0`
- `0x180009210`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000911d`
- `ntdll!EtwEventWrite` at `0x180009197`
- `ntdll!EtwEventWrite` at `0x18000911d`
- `ntdll!EtwEventWrite` at `0x180009197`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009146`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009146`

## pseudocode

```c
__int64 __fastcall FWGetConfig2(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int64 a5, int *a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v10 = Int_FWGetOrSetConfig(1u, a1, a2, a3, a4, a5, a6);
  v11 = v10;
  if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  return v11;
}

```

## disassembly

```asm
0x1800090d0  push    rbx
0x1800090d2  push    rbp
0x1800090d3  push    rsi
0x1800090d4  push    rdi
0x1800090d5  push    r12
0x1800090d7  push    r13
0x1800090d9  push    r14
0x1800090db  push    r15
0x1800090dd  sub     rsp, 48h
0x1800090e1  mov     r14, [rsp+88h+arg_20]
0x1800090e9  mov     rbx, rcx
0x1800090ec  mov     rcx, cs:g_Provider
0x1800090f3  mov     ebp, r9d
0x1800090f6  mov     r15, [rsp+88h+arg_28]
0x1800090fe  mov     esi, r8d
0x180009101  mov     r12, [rsp+88h+arg_30]
0x180009109  mov     edi, edx
0x18000910b  test    rcx, rcx
0x18000910e  jz      short loc_180009129
0x180009110  xor     r9d, r9d
0x180009113  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000911a  xor     r8d, r8d
0x18000911d  call    cs:__imp_EtwEventWrite
0x180009124  nop     dword ptr [rax+rax+00h]
0x180009129  mov     rcx, cs:WPP_GLOBAL_Control
0x180009130  lea     r13, WPP_GLOBAL_Control
0x180009137  cmp     rcx, r13
0x18000913a  jz      short loc_180009146
0x18000913c  test    byte ptr [rcx+1Ch], 8
0x180009140  jnz     loc_1800091E3
0x180009146  call    cs:__imp_GetTickCount64
0x18000914d  nop     dword ptr [rax+rax+00h]
0x180009152  mov     [rsp+88h+var_50], r12
0x180009157  mov     r9d, esi
0x18000915a  mov     [rsp+88h+var_58], r15
0x18000915f  mov     r8d, edi
0x180009162  mov     [rsp+88h+var_60], r14
0x180009167  mov     rdx, rbx
0x18000916a  mov     ecx, 1
0x18000916f  mov     [rsp+88h+var_68], ebp
0x180009173  call    Int_FWGetOrSetConfig
0x180009178  mov     ebx, eax
0x18000917a  test    eax, eax
0x18000917c  jnz     short loc_1800091B7
0x18000917e  mov     rcx, cs:g_Provider
0x180009185  test    rcx, rcx
0x180009188  jz      short loc_1800091A3
0x18000918a  xor     r9d, r9d
0x18000918d  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180009194  xor     r8d, r8d
0x180009197  call    cs:__imp_EtwEventWrite
0x18000919e  nop     dword ptr [rax+rax+00h]
0x1800091a3  mov     eax, ebx
0x1800091a5  add     rsp, 48h
0x1800091a9  pop     r15
0x1800091ab  pop     r14
0x1800091ad  pop     r13
0x1800091af  pop     r12
0x1800091b1  pop     rdi
0x1800091b2  pop     rsi
0x1800091b3  pop     rbp
0x1800091b4  pop     rbx
0x1800091b5  retn
0x1800091b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091be  cmp     rcx, r13
0x1800091c1  jz      short loc_18000917E
0x1800091c3  test    byte ptr [rcx+1Ch], 1
0x1800091c7  jz      short loc_18000917E
0x1800091c9  mov     rcx, [rcx+10h]
0x1800091cd  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800091d4  mov     edx, 6Ah ; 'j'
0x1800091d9  mov     r9d, ebx
0x1800091dc  call    WPP_SF_d
0x1800091e1  jmp     short loc_18000917E
0x1800091e3  mov     rcx, [rcx+10h]
0x1800091e7  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800091ee  mov     edx, 69h ; 'i'
0x1800091f3  call    WPP_SF_
0x1800091f8  jmp     loc_180009146
```
