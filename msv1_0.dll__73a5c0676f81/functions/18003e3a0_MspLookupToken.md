# MspLookupToken

- ea: `0x18003e3a0`
- end: `0x18003e68c`
- name: `MspLookupToken`
- size: `748`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x18000dab4`
- `0x18000db30`
- `0x18000dc18`
- `0x18002ee7c`
- `0x18003e3a0`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlCheckTokenMembershipEx` at `0x18003e4c1`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18003e4c1`
- `ntdll!NtClose` at `0x18003e65e`
- `ntdll!NtClose` at `0x18003e65e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MspLookupToken(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  _DWORD *v7; // rdi
  _QWORD *v8; // r14
  _DWORD *v10; // rsi
  int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  _DWORD *v15; // r15
  __int64 v17; // [rsp+20h] [rbp-50h] BYREF
  __int64 v18; // [rsp+28h] [rbp-48h] BYREF
  __int128 v19; // [rsp+30h] [rbp-40h]
  __int64 v20; // [rsp+40h] [rbp-30h]
  __int128 v21; // [rsp+48h] [rbp-28h] BYREF
  __int128 v22; // [rsp+58h] [rbp-18h]
  HANDLE Handle; // [rsp+A0h] [rbp+30h] BYREF
  char v24; // [rsp+B8h] [rbp+48h] BYREF

  v7 = a7;
  v8 = a5;
  v10 = a6;
  v24 = 0;
  *a7 = -1073741823;
  *v8 = 0;
  *v10 = 0;
  Handle = 0;
  v17 = 0;
  v18 = a1;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v19 = 0;
  if ( a4 < 0xC )
  {
    v11 = -1073741811;
LABEL_42:
    NlpFreeClientBuffer(&v18);
    return (unsigned int)v11;
  }
  v11 = ((__int64 (__fastcall *)(__int128 *))LsaFunctions->GetClientInfo)(&v21);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 57;
LABEL_7:
      v14 = (unsigned int)v11;
LABEL_8:
      WPP_SF_d(v12[2], v13, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, v14);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( !(_BYTE)v22 )
  {
    v11 = -1073741790;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v13 = 58;
    goto LABEL_13;
  }
  v11 = RtlCheckTokenMembershipEx(*((_QWORD *)&v22 + 1), NtLmGlobalCscServiceSid, 0, &v24);
  if ( v11 >= 0 )
  {
    if ( v24 )
    {
      v11 = NlpAllocateClientBuffer(&v18, 4, 4);
      if ( v11 >= 0 )
      {
        **((_DWORD **)&v19 + 1) = 0;
        v15 = (_DWORD *)*((_QWORD *)&v19 + 1);
        v11 = ((__int64 (__fastcall *)(__int64, HANDLE *))LsaFunctions->OpenTokenByLogonId)(a2 + 4, &Handle);
        if ( v11 >= 0 )
        {
          v11 = ((__int64 (__fastcall *)(HANDLE, __int64 *))LsaFunctions->DuplicateTokenHandle)(Handle, &v17);
          if ( v11 >= 0 )
          {
            *v15 = v17;
            v11 = NlpFlushClientBuffer(&v18, v8);
            if ( v11 >= 0 )
            {
              *v10 = 4;
              *v7 = 0;
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v13 = 64;
                goto LABEL_7;
              }
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 63;
              goto LABEL_7;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 62;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 61;
          goto LABEL_7;
        }
      }
      goto LABEL_39;
    }
    v11 = -1073741790;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v13 = 60;
LABEL_13:
    v14 = 3221225506LL;
    goto LABEL_8;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 59;
    goto LABEL_7;
  }
LABEL_39:
  if ( Handle )
    NtClose(Handle);
  if ( v11 < 0 )
    goto LABEL_42;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003e3a0  mov     [rsp-28h+arg_8], rbx
0x18003e3a5  mov     [rsp-28h+arg_10], rsi
0x18003e3aa  push    rbp
0x18003e3ab  push    rdi
0x18003e3ac  push    r13
0x18003e3ae  push    r14
0x18003e3b0  push    r15
0x18003e3b2  mov     rbp, rsp
0x18003e3b5  sub     rsp, 70h
0x18003e3b9  mov     rdi, [rbp+arg_30]
0x18003e3bd  xorps   xmm0, xmm0
0x18003e3c0  mov     r14, [rbp+arg_20]
0x18003e3c4  mov     r13, rdx
0x18003e3c7  mov     rsi, [rbp+arg_28]
0x18003e3cb  mov     [rbp+arg_18], 0
0x18003e3cf  mov     dword ptr [rdi], 0C0000001h
0x18003e3d5  mov     qword ptr [r14], 0
0x18003e3dc  mov     dword ptr [rsi], 0
0x18003e3e2  mov     [rbp+Handle], 0
0x18003e3ea  mov     [rbp+var_50], 0
0x18003e3f2  mov     [rbp+var_48], rcx
0x18003e3f6  mov     [rbp+var_30], 0
0x18003e3fe  movups  [rbp+var_28], xmm0
0x18003e402  movups  [rbp+var_18], xmm0
0x18003e406  movdqu  [rbp+var_40], xmm0
0x18003e40b  cmp     r9d, 0Ch
0x18003e40f  jnb     short loc_18003E41B
0x18003e411  mov     ebx, 0C000000Dh
0x18003e416  jmp     loc_18003E668
0x18003e41b  mov     rax, cs:LsaFunctions
0x18003e422  lea     rcx, [rbp+var_28]
0x18003e426  mov     rax, [rax+80h]
0x18003e42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e432  mov     ebx, eax
0x18003e434  test    eax, eax
0x18003e436  jns     short loc_18003E476
0x18003e438  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e43f  lea     rax, WPP_GLOBAL_Control
0x18003e446  cmp     rcx, rax
0x18003e449  jz      loc_18003E655
0x18003e44f  test    byte ptr [rcx+1Ch], 1
0x18003e453  jz      loc_18003E655
0x18003e459  mov     edx, 39h ; '9'
0x18003e45e  mov     r9d, ebx
0x18003e461  mov     rcx, [rcx+10h]
0x18003e465  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003e46c  call    WPP_SF_d
0x18003e471  jmp     loc_18003E655
0x18003e476  cmp     byte ptr [rbp+var_18], 0
0x18003e47a  jnz     short loc_18003E4AF
0x18003e47c  mov     ebx, 0C0000022h
0x18003e481  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e488  lea     rax, WPP_GLOBAL_Control
0x18003e48f  cmp     rcx, rax
0x18003e492  jz      loc_18003E655
0x18003e498  test    byte ptr [rcx+1Ch], 1
0x18003e49c  jz      loc_18003E655
0x18003e4a2  mov     edx, 3Ah ; ':'
0x18003e4a7  mov     r9d, 0C0000022h
0x18003e4ad  jmp     short loc_18003E461
0x18003e4af  mov     rdx, cs:NtLmGlobalCscServiceSid
0x18003e4b6  lea     r9, [rbp+arg_18]
0x18003e4ba  mov     rcx, qword ptr [rbp+var_18+8]
0x18003e4be  xor     r8d, r8d
0x18003e4c1  call    cs:__imp_RtlCheckTokenMembershipEx
0x18003e4c7  mov     ebx, eax
0x18003e4c9  test    eax, eax
0x18003e4cb  jns     short loc_18003E4F8
0x18003e4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4d4  lea     rax, WPP_GLOBAL_Control
0x18003e4db  cmp     rcx, rax
0x18003e4de  jz      loc_18003E655
0x18003e4e4  test    byte ptr [rcx+1Ch], 1
0x18003e4e8  jz      loc_18003E655
0x18003e4ee  mov     edx, 3Bh ; ';'
0x18003e4f3  jmp     loc_18003E45E
0x18003e4f8  cmp     [rbp+arg_18], 0
0x18003e4fc  jnz     short loc_18003E52E
0x18003e4fe  mov     ebx, 0C0000022h
0x18003e503  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e50a  lea     rax, WPP_GLOBAL_Control
0x18003e511  cmp     rcx, rax
0x18003e514  jz      loc_18003E655
0x18003e51a  test    byte ptr [rcx+1Ch], 1
0x18003e51e  jz      loc_18003E655
0x18003e524  mov     edx, 3Ch ; '<'
0x18003e529  jmp     loc_18003E4A7
0x18003e52e  mov     eax, 4
0x18003e533  lea     rcx, [rbp+var_48]
0x18003e537  mov     r8d, eax
0x18003e53a  mov     edx, eax
0x18003e53c  call    NlpAllocateClientBuffer
0x18003e541  mov     ebx, eax
0x18003e543  test    eax, eax
0x18003e545  jns     short loc_18003E572
0x18003e547  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e54e  lea     rax, WPP_GLOBAL_Control
0x18003e555  cmp     rcx, rax
0x18003e558  jz      loc_18003E655
0x18003e55e  test    byte ptr [rcx+1Ch], 1
0x18003e562  jz      loc_18003E655
0x18003e568  mov     edx, 3Dh ; '='
0x18003e56d  jmp     loc_18003E45E
0x18003e572  mov     rax, qword ptr [rbp+var_40+8]
0x18003e576  lea     rdx, [rbp+Handle]
0x18003e57a  xor     ecx, ecx
0x18003e57c  mov     [rax], ecx
0x18003e57e  lea     rcx, [r13+4]
0x18003e582  mov     rax, cs:LsaFunctions
0x18003e589  mov     r15, qword ptr [rbp+var_40+8]
0x18003e58d  mov     rax, [rax+170h]
0x18003e594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e599  mov     ebx, eax
0x18003e59b  test    eax, eax
0x18003e59d  jns     short loc_18003E5CA
0x18003e59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5a6  lea     rax, WPP_GLOBAL_Control
0x18003e5ad  cmp     rcx, rax
0x18003e5b0  jz      loc_18003E655
0x18003e5b6  test    byte ptr [rcx+1Ch], 1
0x18003e5ba  jz      loc_18003E655
0x18003e5c0  mov     edx, 3Eh ; '>'
0x18003e5c5  jmp     loc_18003E45E
0x18003e5ca  mov     rax, cs:LsaFunctions
0x18003e5d1  lea     rdx, [rbp+var_50]
0x18003e5d5  mov     rcx, [rbp+Handle]
0x18003e5d9  mov     rax, [rax+1B8h]
0x18003e5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5e5  mov     ebx, eax
0x18003e5e7  test    eax, eax
0x18003e5e9  jns     short loc_18003E60E
0x18003e5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5f2  lea     rax, WPP_GLOBAL_Control
0x18003e5f9  cmp     rcx, rax
0x18003e5fc  jz      short loc_18003E655
0x18003e5fe  test    byte ptr [rcx+1Ch], 1
0x18003e602  jz      short loc_18003E655
0x18003e604  mov     edx, 3Fh ; '?'
0x18003e609  jmp     loc_18003E45E
0x18003e60e  mov     eax, dword ptr [rbp+var_50]
0x18003e611  lea     rcx, [rbp+var_48]
0x18003e615  mov     rdx, r14
0x18003e618  mov     [r15], eax
0x18003e61b  call    NlpFlushClientBuffer
0x18003e620  mov     ebx, eax
0x18003e622  test    eax, eax
0x18003e624  jns     short loc_18003E649
0x18003e626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e62d  lea     rax, WPP_GLOBAL_Control
0x18003e634  cmp     rcx, rax
0x18003e637  jz      short loc_18003E655
0x18003e639  test    byte ptr [rcx+1Ch], 1
0x18003e63d  jz      short loc_18003E655
0x18003e63f  mov     edx, 40h ; '@'
0x18003e644  jmp     loc_18003E45E
0x18003e649  mov     dword ptr [rsi], 4
0x18003e64f  mov     dword ptr [rdi], 0
0x18003e655  mov     rcx, [rbp+Handle]; Handle
0x18003e659  test    rcx, rcx
0x18003e65c  jz      short loc_18003E664
0x18003e65e  call    cs:__imp_NtClose
0x18003e664  test    ebx, ebx
0x18003e666  jns     short loc_18003E671
0x18003e668  lea     rcx, [rbp+var_48]
0x18003e66c  call    NlpFreeClientBuffer
0x18003e671  lea     r11, [rsp+70h+var_s0]
0x18003e676  mov     eax, ebx
0x18003e678  mov     rbx, [r11+38h]
0x18003e67c  mov     rsi, [r11+40h]
0x18003e680  mov     rsp, r11
0x18003e683  pop     r15
0x18003e685  pop     r14
0x18003e687  pop     r13
0x18003e689  pop     rdi
0x18003e68a  pop     rbp
0x18003e68b  retn
```
