# DwmpGetAnimationCommitHandle

- ea: `0x1800114e0`
- end: `0x1800115ab`
- name: `DwmpGetAnimationCommitHandle`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x18000d0a0`
- `0x1800114e0`

## pseudocode

```c
__int64 __fastcall DwmpGetAnimationCommitHandle(CApiPortClient *a1, _QWORD *a2)
{
  __int128 v4; // xmm0
  int v5; // ebx
  __int64 v6; // rdx
  int v7; // [rsp+20h] [rbp-48h]
  int v8; // [rsp+30h] [rbp-38h] BYREF
  int v9; // [rsp+38h] [rbp-30h] BYREF
  __int128 v10; // [rsp+3Ch] [rbp-2Ch]
  __int64 v11; // [rsp+4Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a2 )
    return 2147942487LL;
  v4 = *(_OWORD *)a1;
  *a2 = 0;
  v11 = 0;
  v8 = 0;
  v9 = 1073741928;
  v10 = v4;
  v5 = CApiPortClient::SendRequest(a1, &v9, 28, &v8, &v9, 28);
  if ( v5 < 0 )
  {
    v6 = 217;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\animationcoordination.cpp",
      (const char *)(unsigned int)v5,
      v7);
    return (unsigned int)v5;
  }
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = 218;
    goto LABEL_5;
  }
  *a2 = v11;
  return 0;
}

```

## disassembly

```asm
0x1800114e0  mov     [rsp+arg_10], rbx
0x1800114e5  push    rdi
0x1800114e6  sub     rsp, 60h
0x1800114ea  mov     rax, cs:__security_cookie
0x1800114f1  xor     rax, rsp
0x1800114f4  mov     [rsp+68h+var_10], rax
0x1800114f9  mov     rdi, rdx
0x1800114fc  test    rdx, rdx
0x1800114ff  jnz     short loc_18001150B
0x180011501  mov     eax, 80070057h
0x180011506  jmp     loc_180011590
0x18001150b  movups  xmm0, xmmword ptr [rcx]
0x18001150e  xor     eax, eax
0x180011510  mov     qword ptr [rdx], 0
0x180011517  mov     [rsp+68h+var_1C], rax
0x18001151c  lea     r9, [rsp+68h+var_38]; int *
0x180011521  mov     [rsp+68h+var_38], eax
0x180011525  lea     rdx, [rsp+68h+var_30]; void *
0x18001152a  mov     eax, 1Ch
0x18001152f  mov     [rsp+68h+var_30], 40000068h
0x180011537  mov     [rsp+68h+var_40], ax; __int16
0x18001153c  mov     r8d, eax; __int16
0x18001153f  lea     rax, [rsp+68h+var_30]
0x180011544  mov     [rsp+68h+var_48], rax; int
0x180011549  movdqu  [rsp+68h+var_2C], xmm0
0x18001154f  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180011554  mov     ebx, eax
0x180011556  test    eax, eax
0x180011558  jns     short loc_180011577
0x18001155a  mov     edx, 0D9h; void *
0x18001155f  mov     rcx, [rsp+68h]; this
0x180011564  lea     r8, aClientcoreWind_2; "clientcore\\windows\\dwm\\dwmapi\\anima"...
0x18001156b  mov     r9d, ebx; char *
0x18001156e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011573  mov     eax, ebx
0x180011575  jmp     short loc_180011590
0x180011577  mov     ebx, [rsp+68h+var_38]
0x18001157b  test    ebx, ebx
0x18001157d  jns     short loc_180011586
0x18001157f  mov     edx, 0DAh
0x180011584  jmp     short loc_18001155F
0x180011586  mov     rax, [rsp+68h+var_1C]
0x18001158b  mov     [rdi], rax
0x18001158e  xor     eax, eax
0x180011590  mov     rcx, [rsp+68h+var_10]
0x180011595  xor     rcx, rsp; StackCookie
0x180011598  call    __security_check_cookie
0x18001159d  mov     rbx, [rsp+68h+arg_10]
0x1800115a5  add     rsp, 60h
0x1800115a9  pop     rdi
0x1800115aa  retn
```
