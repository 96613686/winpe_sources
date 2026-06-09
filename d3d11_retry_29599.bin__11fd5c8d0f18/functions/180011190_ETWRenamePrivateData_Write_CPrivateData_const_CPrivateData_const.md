# ETWRenamePrivateData::Write(CPrivateData const &,CPrivateData const &)

- ea: `0x180011190`
- end: `0x1800112a7`
- name: `?Write@ETWRenamePrivateData@@QEBAXAEBVCPrivateData@@0@Z`
- size: `279`
- prototype: `void __fastcall(ETWRenamePrivateData *__hidden this, const struct CPrivateData *, const struct CPrivateData *)`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c34c`
- `0x18000c730`
- `0x18000cbb4`
- `0x18000cfa4`
- `0x18000d380`
- `0x18000d79c`
- `0x18000dcc8`
- `0x18000e0f0`
- `0x18000e590`
- `0x18000ecf0`
- `0x18000f490`
- `0x18000fd80`
- `0x180010760`
- `0x180011580`

## callees

- `0x180011190`
- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180011274`
- `ntdll!EtwEventWrite` at `0x180011274`

## pseudocode

```c
void __fastcall ETWRenamePrivateData::Write(
        ETWRenamePrivateData *this,
        const struct CPrivateData *a2,
        const struct CPrivateData *a3)
{
  int v3; // r11d
  int v4; // r10d
  const struct CPrivateData *v5; // r9
  const struct CPrivateData *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  _BYTE v12[4]; // [rsp+20h] [rbp-19h] BYREF
  int v13; // [rsp+24h] [rbp-15h] BYREF
  int v14; // [rsp+28h] [rbp-11h] BYREF
  _QWORD v15[5]; // [rsp+30h] [rbp-9h] BYREF
  int v16; // [rsp+58h] [rbp+1Fh]
  int v17; // [rsp+5Ch] [rbp+23h]
  int *v18; // [rsp+60h] [rbp+27h]
  __int64 v19; // [rsp+68h] [rbp+2Fh]
  const struct CPrivateData *v20; // [rsp+70h] [rbp+37h]
  int v21; // [rsp+78h] [rbp+3Fh]
  int v22; // [rsp+7Ch] [rbp+43h]

  v3 = 0;
  v12[0] = 0;
  v4 = 0;
  v13 = 0;
  v5 = (const struct CPrivateData *)v12;
  v7 = (const struct CPrivateData *)v12;
  v14 = 0;
  if ( !*((_DWORD *)a2 + 3) )
  {
    v8 = *((_DWORD *)a2 + 2);
    if ( v8 )
    {
      if ( v8 <= 8 )
        v5 = a2;
      else
        v5 = *(const struct CPrivateData **)a2;
      v3 = *((_DWORD *)a2 + 2);
      v13 = v3;
    }
  }
  if ( !*((_DWORD *)a3 + 3) )
  {
    v9 = *((_DWORD *)a3 + 2);
    if ( v9 )
    {
      if ( v9 <= 8 )
        v7 = a3;
      else
        v7 = *(const struct CPrivateData **)a3;
      v4 = *((_DWORD *)a3 + 2);
      v14 = v4;
    }
  }
  if ( v5 != v7 )
  {
    v10 = *((_QWORD *)this + 1);
    v15[0] = (char *)this + 24;
    v20 = v7;
    v11 = (_QWORD *)*((_QWORD *)this + 2);
    v15[2] = &v13;
    v15[4] = v5;
    v18 = &v14;
    v15[1] = 8;
    v15[3] = 4;
    v16 = v3;
    v17 = 0;
    v19 = 4;
    v21 = v4;
    v22 = 0;
    EtwEventWrite(*v11, v10, 5, v15);
  }
}

```

## disassembly

```asm
0x180011190  mov     [rsp-8+arg_8], rbx
0x180011195  push    rbp
0x180011196  lea     rbp, [rsp-57h]
0x18001119b  sub     rsp, 90h
0x1800111a2  mov     rax, cs:__security_cookie
0x1800111a9  xor     rax, rsp
0x1800111ac  mov     [rbp+57h+var_10], rax
0x1800111b0  xor     r11d, r11d
0x1800111b3  mov     [rbp+57h+var_70], 0
0x1800111b7  xor     r10d, r10d
0x1800111ba  mov     [rbp+57h+var_6C], r11d
0x1800111be  lea     r9, [rbp+57h+var_70]
0x1800111c2  mov     rbx, rcx
0x1800111c5  lea     rcx, [rbp+57h+var_70]
0x1800111c9  mov     [rbp+57h+var_68], r10d
0x1800111cd  cmp     [rdx+0Ch], r10d
0x1800111d1  jnz     short loc_1800111EC
0x1800111d3  mov     eax, [rdx+8]
0x1800111d6  test    eax, eax
0x1800111d8  jz      short loc_1800111EC
0x1800111da  cmp     eax, 8
0x1800111dd  jbe     loc_180011297
0x1800111e3  mov     r9, [rdx]
0x1800111e6  mov     r11d, eax
0x1800111e9  mov     [rbp+57h+var_6C], eax
0x1800111ec  cmp     [r8+0Ch], r10d
0x1800111f0  jnz     short loc_18001120C
0x1800111f2  mov     eax, [r8+8]
0x1800111f6  test    eax, eax
0x1800111f8  jz      short loc_18001120C
0x1800111fa  cmp     eax, 8
0x1800111fd  jbe     loc_18001129F
0x180011203  mov     rcx, [r8]
0x180011206  mov     r10d, eax
0x180011209  mov     [rbp+57h+var_68], eax
0x18001120c  cmp     r9, rcx
0x18001120f  jz      short loc_18001127A
0x180011211  mov     rdx, [rbx+8]
0x180011215  lea     rax, [rbx+18h]
0x180011219  mov     [rbp+57h+var_60], rax
0x18001121d  mov     r8d, 5
0x180011223  mov     [rbp+57h+var_20], rcx
0x180011227  lea     rax, [rbp+57h+var_6C]
0x18001122b  mov     rcx, [rbx+10h]
0x18001122f  mov     [rbp+57h+var_50], rax
0x180011233  lea     rax, [rbp+57h+var_68]
0x180011237  mov     [rbp+57h+var_40], r9
0x18001123b  lea     r9, [rbp+57h+var_60]
0x18001123f  mov     [rbp+57h+var_30], rax
0x180011243  mov     [rbp+57h+var_58], 8
0x18001124b  mov     [rbp+57h+var_48], 4
0x180011253  mov     [rbp+57h+var_38], r11d
0x180011257  mov     [rbp+57h+var_34], 0
0x18001125e  mov     [rbp+57h+var_28], 4
0x180011266  mov     [rbp+57h+var_18], r10d
0x18001126a  mov     [rbp+57h+var_14], 0
0x180011271  mov     rcx, [rcx]
0x180011274  call    cs:__imp_EtwEventWrite
0x18001127a  mov     rcx, [rbp+57h+var_10]
0x18001127e  xor     rcx, rsp; StackCookie
0x180011281  call    __security_check_cookie
0x180011286  mov     rbx, [rsp+90h+arg_8]
0x18001128e  add     rsp, 90h
0x180011295  pop     rbp
0x180011296  retn
0x180011297  mov     r9, rdx
0x18001129a  jmp     loc_1800111E6
0x18001129f  mov     rcx, r8
0x1800112a2  jmp     loc_180011206
```
