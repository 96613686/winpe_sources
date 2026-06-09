# RpcOpenMMFilterHandle

- ea: `0x180014510`
- end: `0x1800146ed`
- name: `RpcOpenMMFilterHandle`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18000e510`
- `0x18000fbb4`
- `0x180014510`
- `0x180017e80`
- `0x180023c34`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800146c2`
- `RPCRT4!RpcRevertToSelf` at `0x1800146c2`

## pseudocode

```c
__int64 __fastcall RpcOpenMMFilterHandle(__int64 a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  _DWORD v17[4]; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v18[176]; // [rsp+40h] [rbp-D8h] BYREF

  memset_0(v18, 0, 0xA8u);
  v17[0] = 0;
  v7 = SPDImpersonateClient(v17);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 149;
LABEL_5:
      v11 = v7;
LABEL_29:
      WPP_SF_d(v9[2], v10, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids, v11);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  if ( a2 >= 2 )
  {
    v8 = 50;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v10 = 150;
    goto LABEL_10;
  }
  if ( !a3 || !a4 )
  {
    v11 = 87;
    v8 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 151;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  v12 = *(int **)(a3 + 8);
  if ( !v12 || *(_DWORD *)a3 != 1 )
  {
    v11 = 87;
    v8 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 152;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  if ( *v12 > 2 )
  {
    v8 = 124;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v10 = 153;
LABEL_10:
    v11 = v8;
    goto LABEL_29;
  }
  CopyOldToNewMMFilter(v12, (__int64)v18);
  v7 = OpenMMFilterHandleInternal(v14, v13, (__int64)v18, v15, a4);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 154;
      goto LABEL_5;
    }
  }
LABEL_30:
  if ( v17[0] )
    RpcRevertToSelf();
  return v8;
}

```

## disassembly

```asm
0x180014510  mov     [rsp+arg_0], rbx
0x180014515  push    rbp
0x180014516  push    rsi
0x180014517  push    rdi
0x180014518  sub     rsp, 100h
0x18001451f  mov     rax, cs:__security_cookie
0x180014526  xor     rax, rsp
0x180014529  mov     [rsp+118h+var_28], rax
0x180014531  mov     rdi, r8
0x180014534  lea     rcx, [rsp+118h+var_D8]; void *
0x180014539  mov     ebp, edx
0x18001453b  mov     r8d, 0A8h; Size
0x180014541  xor     edx, edx; Val
0x180014543  mov     rsi, r9
0x180014546  call    memset_0
0x18001454b  lea     rcx, [rsp+118h+var_E8]
0x180014550  mov     [rsp+118h+var_E8], 0
0x180014558  call    SPDImpersonateClient
0x18001455d  mov     ebx, eax
0x18001455f  test    eax, eax
0x180014561  jz      short loc_180014591
0x180014563  mov     rcx, cs:WPP_GLOBAL_Control
0x18001456a  lea     rdx, WPP_GLOBAL_Control
0x180014571  cmp     rcx, rdx
0x180014574  jz      loc_1800146BB
0x18001457a  test    byte ptr [rcx+1Ch], 10h
0x18001457e  jz      loc_1800146BB
0x180014584  mov     edx, 95h
0x180014589  mov     r9d, eax
0x18001458c  jmp     loc_1800146AB
0x180014591  cmp     ebp, 2
0x180014594  jb      short loc_1800145C7
0x180014596  mov     ebx, 32h ; '2'
0x18001459b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145a2  lea     rdx, WPP_GLOBAL_Control
0x1800145a9  cmp     rcx, rdx
0x1800145ac  jz      loc_1800146BB
0x1800145b2  test    byte ptr [rcx+1Ch], 10h
0x1800145b6  jz      loc_1800146BB
0x1800145bc  lea     edx, [rbx+64h]
0x1800145bf  mov     r9d, ebx
0x1800145c2  jmp     loc_1800146AB
0x1800145c7  test    rdi, rdi
0x1800145ca  jz      loc_180014685
0x1800145d0  test    rsi, rsi
0x1800145d3  jz      loc_180014685
0x1800145d9  mov     rcx, [rdi+8]
0x1800145dd  test    rcx, rcx
0x1800145e0  jz      short loc_18001465D
0x1800145e2  cmp     dword ptr [rdi], 1
0x1800145e5  jnz     short loc_18001465D
0x1800145e7  cmp     dword ptr [rcx], 2
0x1800145ea  jle     short loc_180014617
0x1800145ec  mov     ebx, 7Ch ; '|'
0x1800145f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145f8  lea     rdx, WPP_GLOBAL_Control
0x1800145ff  cmp     rcx, rdx
0x180014602  jz      loc_1800146BB
0x180014608  test    byte ptr [rcx+1Ch], 10h
0x18001460c  jz      loc_1800146BB
0x180014612  lea     edx, [rbx+1Dh]
0x180014615  jmp     short loc_1800145BF
0x180014617  lea     rdx, [rsp+118h+var_D8]
0x18001461c  call    CopyOldToNewMMFilter
0x180014621  lea     r8, [rsp+118h+var_D8]
0x180014626  mov     [rsp+118h+var_F8], rsi
0x18001462b  call    OpenMMFilterHandleInternal
0x180014630  mov     ebx, eax
0x180014632  test    eax, eax
0x180014634  jz      loc_1800146BB
0x18001463a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014641  lea     rdx, WPP_GLOBAL_Control
0x180014648  cmp     rcx, rdx
0x18001464b  jz      short loc_1800146BB
0x18001464d  test    byte ptr [rcx+1Ch], 10h
0x180014651  jz      short loc_1800146BB
0x180014653  mov     edx, 9Ah
0x180014658  jmp     loc_180014589
0x18001465d  mov     r9d, 57h ; 'W'
0x180014663  mov     ebx, r9d
0x180014666  mov     rcx, cs:WPP_GLOBAL_Control
0x18001466d  lea     rdx, WPP_GLOBAL_Control
0x180014674  cmp     rcx, rdx
0x180014677  jz      short loc_1800146BB
0x180014679  test    byte ptr [rcx+1Ch], 10h
0x18001467d  jz      short loc_1800146BB
0x18001467f  lea     edx, [r9+41h]
0x180014683  jmp     short loc_1800146AB
0x180014685  mov     r9d, 57h ; 'W'
0x18001468b  mov     ebx, r9d
0x18001468e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014695  lea     rdx, WPP_GLOBAL_Control
0x18001469c  cmp     rcx, rdx
0x18001469f  jz      short loc_1800146BB
0x1800146a1  test    byte ptr [rcx+1Ch], 10h
0x1800146a5  jz      short loc_1800146BB
0x1800146a7  lea     edx, [r9+40h]
0x1800146ab  mov     rcx, [rcx+10h]
0x1800146af  lea     r8, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids
0x1800146b6  call    WPP_SF_d
0x1800146bb  cmp     [rsp+118h+var_E8], 0
0x1800146c0  jz      short loc_1800146C8
0x1800146c2  call    cs:__imp_RpcRevertToSelf
0x1800146c8  mov     eax, ebx
0x1800146ca  mov     rcx, [rsp+118h+var_28]
0x1800146d2  xor     rcx, rsp; StackCookie
0x1800146d5  call    __security_check_cookie
0x1800146da  mov     rbx, [rsp+118h+arg_0]
0x1800146e2  add     rsp, 100h
0x1800146e9  pop     rdi
0x1800146ea  pop     rsi
0x1800146eb  pop     rbp
0x1800146ec  retn
```
