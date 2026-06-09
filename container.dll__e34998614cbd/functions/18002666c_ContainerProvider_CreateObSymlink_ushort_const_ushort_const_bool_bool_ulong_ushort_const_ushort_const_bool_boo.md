# ContainerProvider::CreateObSymlink<ushort const *,ushort const *,bool &,bool &,ulong &>(ushort const * &&,ushort const * &&,bool &,bool &,ulong &)

- ea: `0x18002666c`
- end: `0x1800267a7`
- name: `??$CreateObSymlink@PEBGPEBGAEA_NAEA_NAEAK@ContainerProvider@@SAX$$QEAPEBG0AEA_N1AEAK@Z`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800268b8`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x18002666c`

## pseudocode

```c
int __fastcall ContainerProvider::CreateObSymlink<unsigned short const *,unsigned short const *,bool &,bool &,unsigned long &>(
        const WCHAR **a1,
        const WCHAR **a2,
        char *a3,
        char *a4,
        int *a5)
{
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rbx
  char v11; // r8
  char v12; // cl
  const WCHAR *v13; // rdx
  int v14; // r11d
  __int64 v15; // rax
  int v16; // r9d
  const WCHAR *v17; // r8
  __int64 v18; // rcx
  int v19; // ecx
  char v21; // [rsp+30h] [rbp-71h] BYREF
  char v22; // [rsp+31h] [rbp-70h] BYREF
  int v23; // [rsp+34h] [rbp-6Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+40h] [rbp-61h] BYREF
  const WCHAR *v25; // [rsp+60h] [rbp-41h]
  int v26; // [rsp+68h] [rbp-39h]
  int v27; // [rsp+6Ch] [rbp-35h]
  const WCHAR *v28; // [rsp+70h] [rbp-31h]
  int v29; // [rsp+78h] [rbp-29h]
  int v30; // [rsp+7Ch] [rbp-25h]
  char *v31; // [rsp+80h] [rbp-21h]
  __int64 v32; // [rsp+88h] [rbp-19h]
  char *v33; // [rsp+90h] [rbp-11h]
  __int64 v34; // [rsp+98h] [rbp-9h]
  int *v35; // [rsp+A0h] [rbp-1h]
  __int64 v36; // [rsp+A8h] [rbp+7h]

  v9 = ContainerProvider::Provider();
  v10 = (__int64)v9;
  if ( *(_DWORD *)v9 > 5u )
  {
    v11 = *a4;
    v12 = *a3;
    v13 = *a1;
    v14 = *a5;
    v35 = &v23;
    v33 = &v21;
    v31 = &v22;
    v15 = -1;
    v21 = v11;
    v16 = 2;
    v17 = *a2;
    v23 = v14;
    v22 = v12;
    v36 = 4;
    v34 = 1;
    v32 = 1;
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v17 = &pwszBaseUri;
      v19 = 2;
    }
    v28 = v17;
    v29 = v19;
    v30 = 0;
    if ( v13 )
    {
      do
        ++v15;
      while ( v13[v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v13 = &pwszBaseUri;
    }
    v25 = v13;
    v26 = v16;
    v27 = 0;
    LODWORD(v9) = tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)byte_18003CAEB, 0, 0, 7u, &v24);
  }
  return (int)v9;
}

```

## disassembly

```asm
0x18002666c  push    rbp
0x18002666e  push    rbx
0x18002666f  push    rsi
0x180026670  push    rdi
0x180026671  push    r14
0x180026673  push    r15
0x180026675  lea     rbp, [rsp-27h]
0x18002667a  sub     rsp, 0C8h
0x180026681  mov     rax, cs:__security_cookie
0x180026688  xor     rax, rsp
0x18002668b  mov     [rbp+4Fh+var_40], rax
0x18002668f  mov     rdi, r9
0x180026692  mov     rsi, r8
0x180026695  mov     r14, rdx
0x180026698  mov     r15, rcx
0x18002669b  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x1800266a0  mov     rbx, rax
0x1800266a3  mov     r10d, [rax]
0x1800266a6  cmp     r10d, 5
0x1800266aa  jbe     loc_18002678A
0x1800266b0  mov     r10, [rbp+4Fh+arg_20]
0x1800266b4  lea     rax, [rbp+4Fh+var_BC]
0x1800266b8  mov     r8b, [rdi]
0x1800266bb  mov     cl, [rsi]
0x1800266bd  mov     rdx, [r15]
0x1800266c0  mov     r11d, [r10]
0x1800266c3  xor     r10d, r10d
0x1800266c6  mov     [rbp+4Fh+var_50], rax
0x1800266ca  lea     rax, [rbp+4Fh+var_C0]
0x1800266ce  mov     [rbp+4Fh+var_60], rax
0x1800266d2  lea     rax, [rbp+4Fh+var_BF]
0x1800266d6  mov     [rbp+4Fh+var_70], rax
0x1800266da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800266de  mov     [rbp+4Fh+var_C0], r8b
0x1800266e2  lea     r9d, [r10+2]
0x1800266e6  mov     r8, [r14]
0x1800266e9  mov     [rbp+4Fh+var_BC], r11d
0x1800266ed  mov     [rbp+4Fh+var_BF], cl
0x1800266f0  mov     [rbp+4Fh+var_48], 4
0x1800266f8  mov     [rbp+4Fh+var_58], 1
0x180026700  mov     [rbp+4Fh+var_68], 1
0x180026708  test    r8, r8
0x18002670b  jz      short loc_180026723
0x18002670d  mov     rcx, rax
0x180026710  inc     rcx
0x180026713  cmp     [r8+rcx*2], r10w
0x180026718  jnz     short loc_180026710
0x18002671a  lea     ecx, ds:2[rcx*2]
0x180026721  jmp     short loc_18002672D
0x180026723  lea     r8, pwszBaseUri
0x18002672a  mov     ecx, r9d
0x18002672d  mov     [rbp+4Fh+var_80], r8
0x180026731  mov     [rbp+4Fh+var_78], ecx
0x180026734  mov     [rbp+4Fh+var_74], r10d
0x180026738  test    rdx, rdx
0x18002673b  jz      short loc_180026751
0x18002673d  inc     rax
0x180026740  cmp     [rdx+rax*2], r10w
0x180026745  jnz     short loc_18002673D
0x180026747  lea     r9d, ds:2[rax*2]
0x18002674f  jmp     short loc_180026758
0x180026751  lea     rdx, pwszBaseUri
0x180026758  lea     rax, [rbp+4Fh+var_B0]
0x18002675c  mov     [rbp+4Fh+var_90], rdx
0x180026760  mov     [rbp+4Fh+var_88], r9d
0x180026764  lea     rdx, byte_18003CAEB
0x18002676b  mov     [rsp+0F0h+var_C8], rax
0x180026770  xor     r9d, r9d
0x180026773  xor     r8d, r8d
0x180026776  mov     [rsp+0F0h+var_D0], 7
0x18002677e  mov     rcx, rbx
0x180026781  mov     [rbp+4Fh+var_84], r10d
0x180026785  call    _tlgWriteTransfer_EventWriteTransfer
0x18002678a  mov     rcx, [rbp+4Fh+var_40]
0x18002678e  xor     rcx, rsp; StackCookie
0x180026791  call    __security_check_cookie
0x180026796  add     rsp, 0C8h
0x18002679d  pop     r15
0x18002679f  pop     r14
0x1800267a1  pop     rdi
0x1800267a2  pop     rsi
0x1800267a3  pop     rbx
0x1800267a4  pop     rbp
0x1800267a5  retn
```
