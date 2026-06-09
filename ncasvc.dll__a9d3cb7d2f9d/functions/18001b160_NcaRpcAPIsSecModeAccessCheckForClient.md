# NcaRpcAPIsSecModeAccessCheckForClient

- ea: `0x18001b160`
- end: `0x18001b296`
- name: `NcaRpcAPIsSecModeAccessCheckForClient`
- size: `310`
- prototype: `__int64 __fastcall(unsigned int, __int64, void *)`
- caller_count: `11`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b300`
- `0x18001b3b0`
- `0x18001b460`
- `0x18001b530`
- `0x18001b680`
- `0x18001b760`
- `0x18001b810`
- `0x18001b8d0`
- `0x18001b9a0`
- `0x18001ba70`
- `0x18001bb40`

## callees

- `0x180004f34`
- `0x18001b160`
- `0x18001bc04`
- `0x18001c8e0`

## import_xrefs

- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18001b1bd`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18001b1bd`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsSecModeAccessCheckForClient(unsigned int a1, __int64 a2, void *a3)
{
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rax
  int IsAccessGranted; // eax
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  BOOLEAN pfEnabled; // [rsp+40h] [rbp+8h] BYREF
  int v14; // [rsp+58h] [rbp+20h]

  v4 = (int)a2;
  v5 = a1;
  v14 = 0;
  pfEnabled = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (&PolicyObjectName)[a1]);
  if ( BCryptGetFipsAlgorithmMode(&pfEnabled) >= 0 && pfEnabled )
    v6 = 3;
  else
    v6 = 0;
  IsAccessGranted = NcaRpcAPIsIsAccessGranted(
                      (PSECURITY_DESCRIPTOR)qword_1800295D8[v6 + v5],
                      a3,
                      *((_DWORD *)&AccessCheckAccessRights + v4));
  v8 = IsAccessGranted;
  if ( IsAccessGranted >= 0 )
  {
    if ( v14 )
    {
LABEL_17:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v8 = -2147024891;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v10 = 17;
    v11 = 2147942405LL;
LABEL_16:
    WPP_SF_d(v9[2], v10, &WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids, v11);
    goto LABEL_17;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 16;
    v11 = (unsigned int)IsAccessGranted;
    goto LABEL_16;
  }
LABEL_18:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(v9[2], 18, &WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001b160  mov     rax, rsp
0x18001b163  mov     [rax+10h], rbx
0x18001b167  mov     [rax+18h], rsi
0x18001b16b  push    rdi
0x18001b16c  push    r14
0x18001b16e  push    r15
0x18001b170  sub     rsp, 20h
0x18001b174  mov     rdi, r8
0x18001b177  movsxd  rsi, edx
0x18001b17a  mov     ebx, ecx
0x18001b17c  mov     dword ptr [rax+20h], 0
0x18001b183  mov     byte ptr [rax+8], 0
0x18001b187  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b18e  lea     r14, WPP_GLOBAL_Control
0x18001b195  lea     r15, cs:180000000h
0x18001b19c  cmp     rcx, r14
0x18001b19f  jz      short loc_18001B1B8
0x18001b1a1  test    byte ptr [rcx+1Ch], 8
0x18001b1a5  jz      short loc_18001B1B8
0x18001b1a7  mov     r9, ds:rva ?PolicyObjectName@@3PAPEADA[r15+rbx*8]; char * near * PolicyObjectName ...
0x18001b1af  mov     rcx, [rcx+10h]
0x18001b1b3  call    WPP_SF_s
0x18001b1b8  lea     rcx, [rsp+38h+pfEnabled]; pfEnabled
0x18001b1bd  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18001b1c4  nop     dword ptr [rax+rax+00h]
0x18001b1c9  test    eax, eax
0x18001b1cb  js      short loc_18001B1DB
0x18001b1cd  cmp     [rsp+38h+pfEnabled], 0
0x18001b1d2  jz      short loc_18001B1DB
0x18001b1d4  mov     eax, 3
0x18001b1d9  jmp     short loc_18001B1DD
0x18001b1db  xor     eax, eax
0x18001b1dd  mov     r8d, ds:rva ?AccessCheckAccessRights@@3PAKA[r15+rsi*4]; DesiredAccess
0x18001b1e5  lea     rcx, [rax+rbx]
0x18001b1e9  mov     rcx, rva qword_1800295D8[r15+rcx*8]; pSecurityDescriptor
0x18001b1f1  lea     r9, [rsp+38h+arg_18]
0x18001b1f6  mov     rdx, rdi; BindingHandle
0x18001b1f9  call    NcaRpcAPIsIsAccessGranted
0x18001b1fe  lea     rdi, WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids
0x18001b205  mov     ebx, eax
0x18001b207  test    eax, eax
0x18001b209  jns     short loc_18001B227
0x18001b20b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b212  cmp     rcx, r14
0x18001b215  jz      short loc_18001B27F
0x18001b217  test    byte ptr [rcx+1Ch], 1
0x18001b21b  jz      short loc_18001B260
0x18001b21d  mov     edx, 10h
0x18001b222  mov     r9d, eax
0x18001b225  jmp     short loc_18001B24D
0x18001b227  cmp     [rsp+38h+arg_18], 0
0x18001b22c  jnz     short loc_18001B259
0x18001b22e  mov     ebx, 80070005h
0x18001b233  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b23a  cmp     rcx, r14
0x18001b23d  jz      short loc_18001B27F
0x18001b23f  test    byte ptr [rcx+1Ch], 1
0x18001b243  jz      short loc_18001B260
0x18001b245  mov     edx, 11h
0x18001b24a  mov     r9d, ebx
0x18001b24d  mov     rcx, [rcx+10h]
0x18001b251  mov     r8, rdi
0x18001b254  call    WPP_SF_d
0x18001b259  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b260  cmp     rcx, r14
0x18001b263  jz      short loc_18001B27F
0x18001b265  test    byte ptr [rcx+1Ch], 8
0x18001b269  jz      short loc_18001B27F
0x18001b26b  mov     rcx, [rcx+10h]
0x18001b26f  mov     edx, 12h
0x18001b274  mov     r9d, ebx
0x18001b277  mov     r8, rdi
0x18001b27a  call    WPP_SF_d
0x18001b27f  mov     rsi, [rsp+38h+arg_10]
0x18001b284  mov     eax, ebx
0x18001b286  mov     rbx, [rsp+38h+arg_8]
0x18001b28b  add     rsp, 20h
0x18001b28f  pop     r15
0x18001b291  pop     r14
0x18001b293  pop     rdi
0x18001b294  retn
```
