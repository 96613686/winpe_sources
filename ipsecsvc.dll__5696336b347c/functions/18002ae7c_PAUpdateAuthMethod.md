# PAUpdateAuthMethod

- ea: `0x18002ae7c`
- end: `0x18002afc9`
- name: `PAUpdateAuthMethod`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18002b314`

## callees

- `0x180007584`
- `0x180009314`
- `0x18000e510`
- `0x18001c644`
- `0x180027af4`
- `0x180027e64`
- `0x1800282d0`
- `0x18002830c`
- `0x18002a090`
- `0x18002ae7c`

## pseudocode

```c
__int64 __fastcall PAUpdateAuthMethod(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, unsigned int a5)
{
  __int128 v5; // xmm0
  __int64 MMAuthState; // rax
  __int64 v10; // r8
  _OWORD *v11; // rsi
  __int64 result; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  void *v16; // rdi
  unsigned int v17; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _OWORD v20[2]; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+10h] BYREF
  __int64 v22; // [rsp+70h] [rbp+18h] BYREF

  v22 = a3;
  v5 = *(_OWORD *)(a2 + 8);
  lpMem = 0;
  *a4 = 0;
  v20[0] = v5;
  MMAuthState = FindMMAuthState(v20);
  v11 = (_OWORD *)MMAuthState;
  if ( !MMAuthState )
    goto LABEL_2;
  if ( !*(_DWORD *)(MMAuthState + 16) )
  {
    PADeleteMMAuthState(MMAuthState);
LABEL_2:
    PAAddMMAuthMethods(&v22, 1, a5);
    result = PAAddMMFilterSpecs(a1, a3, a5);
    *a4 = 1;
    return result;
  }
  if ( (unsigned int)EqualAuthMethodData(v10, a3) )
    return 0;
  gbUpdatedAuthMethods = 1;
  v13 = PACreateMMAuthMethods(a3, &lpMem);
  v16 = lpMem;
  v17 = v13;
  if ( v13 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v19 = 17;
LABEL_15:
      WPP_SF_d(v18[2], v19, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v13);
    }
  }
  else
  {
    v20[0] = *v11;
    v13 = IntSetMMAuthMethods(v15, v14, v20, lpMem);
    v17 = v13;
    if ( v13 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v19 = 18;
        goto LABEL_15;
      }
    }
  }
  if ( v16 )
    PAFreeMMAuthMethods(v16);
  return v17;
}

```

## disassembly

```asm
0x18002ae7c  mov     rax, rsp
0x18002ae7f  mov     [rax+8], rbx
0x18002ae83  mov     [rax+18h], r8
0x18002ae87  push    rbp
0x18002ae88  push    rsi
0x18002ae89  push    rdi
0x18002ae8a  sub     rsp, 40h
0x18002ae8e  movups  xmm0, xmmword ptr [rdx+8]
0x18002ae92  mov     rbp, rcx
0x18002ae95  mov     qword ptr [rax+10h], 0
0x18002ae9d  mov     rbx, r8
0x18002aea0  mov     dword ptr [r9], 0
0x18002aea7  lea     rcx, [rax-28h]
0x18002aeab  mov     rdi, r9
0x18002aeae  movdqu  xmmword ptr [rax-28h], xmm0
0x18002aeb3  mov     r8, rdx
0x18002aeb6  call    FindMMAuthState
0x18002aebb  mov     rsi, rax
0x18002aebe  test    rax, rax
0x18002aec1  jnz     short loc_18002AEF8
0x18002aec3  mov     r8d, [rsp+58h+arg_20]
0x18002aecb  lea     rcx, [rsp+58h+arg_10]
0x18002aed0  mov     edx, 1
0x18002aed5  call    PAAddMMAuthMethods
0x18002aeda  mov     r8d, [rsp+58h+arg_20]
0x18002aee2  mov     rdx, rbx
0x18002aee5  mov     rcx, rbp
0x18002aee8  call    PAAddMMFilterSpecs
0x18002aeed  mov     dword ptr [rdi], 1
0x18002aef3  jmp     loc_18002AFBC
0x18002aef8  cmp     dword ptr [rax+10h], 0
0x18002aefc  jnz     short loc_18002AF08
0x18002aefe  mov     rcx, rsi
0x18002af01  call    PADeleteMMAuthState
0x18002af06  jmp     short loc_18002AEC3
0x18002af08  mov     rdx, rbx
0x18002af0b  mov     rcx, r8
0x18002af0e  call    EqualAuthMethodData
0x18002af13  test    eax, eax
0x18002af15  jz      short loc_18002AF1E
0x18002af17  xor     eax, eax
0x18002af19  jmp     loc_18002AFBC
0x18002af1e  lea     rdx, [rsp+58h+lpMem]
0x18002af23  mov     cs:gbUpdatedAuthMethods, 1
0x18002af2d  mov     rcx, rbx
0x18002af30  call    PACreateMMAuthMethods
0x18002af35  mov     rdi, [rsp+58h+lpMem]
0x18002af3a  mov     ebx, eax
0x18002af3c  test    eax, eax
0x18002af3e  jz      short loc_18002AF60
0x18002af40  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af47  lea     rdx, WPP_GLOBAL_Control
0x18002af4e  cmp     rcx, rdx
0x18002af51  jz      short loc_18002AFAD
0x18002af53  test    byte ptr [rcx+1Ch], 10h
0x18002af57  jz      short loc_18002AFAD
0x18002af59  mov     edx, 11h
0x18002af5e  jmp     short loc_18002AF9A
0x18002af60  movups  xmm0, xmmword ptr [rsi]
0x18002af63  mov     r9, rdi
0x18002af66  lea     r8, [rsp+58h+var_28]
0x18002af6b  movdqu  [rsp+58h+var_28], xmm0
0x18002af71  call    IntSetMMAuthMethods
0x18002af76  mov     ebx, eax
0x18002af78  test    eax, eax
0x18002af7a  jz      short loc_18002AFAD
0x18002af7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af83  lea     rdx, WPP_GLOBAL_Control
0x18002af8a  cmp     rcx, rdx
0x18002af8d  jz      short loc_18002AFAD
0x18002af8f  test    byte ptr [rcx+1Ch], 10h
0x18002af93  jz      short loc_18002AFAD
0x18002af95  mov     edx, 12h
0x18002af9a  mov     rcx, [rcx+10h]
0x18002af9e  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002afa5  mov     r9d, eax
0x18002afa8  call    WPP_SF_d
0x18002afad  test    rdi, rdi
0x18002afb0  jz      short loc_18002AFBA
0x18002afb2  mov     rcx, rdi; lpMem
0x18002afb5  call    PAFreeMMAuthMethods
0x18002afba  mov     eax, ebx
0x18002afbc  mov     rbx, [rsp+58h+arg_0]
0x18002afc1  add     rsp, 40h
0x18002afc5  pop     rdi
0x18002afc6  pop     rsi
0x18002afc7  pop     rbp
0x18002afc8  retn
```
