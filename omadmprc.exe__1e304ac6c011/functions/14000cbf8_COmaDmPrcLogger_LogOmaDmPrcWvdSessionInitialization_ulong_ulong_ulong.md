# COmaDmPrcLogger::LogOmaDmPrcWvdSessionInitialization(ulong,ulong,ulong)

- ea: `0x14000cbf8`
- end: `0x14000cd73`
- name: `?LogOmaDmPrcWvdSessionInitialization@COmaDmPrcLogger@@QEAAXKKK@Z`
- size: `379`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400107ec`

## callees

- `0x140001090`
- `0x14000cbf8`
- `0x14000cd7c`
- `0x140015690`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcWvdSessionInitialization(COmaDmPrcLogger *this, int a2, __int64 a3, int a4)
{
  int v5; // edi
  const unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // [rsp+30h] [rbp-69h] BYREF
  int v11; // [rsp+38h] [rbp-61h] BYREF
  int v12; // [rsp+40h] [rbp-59h] BYREF
  __int64 v13; // [rsp+48h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-49h] BYREF
  int *v15; // [rsp+60h] [rbp-39h]
  __int64 v16; // [rsp+68h] [rbp-31h]
  __int64 *v17; // [rsp+70h] [rbp-29h]
  __int64 v18; // [rsp+78h] [rbp-21h]
  int *v19; // [rsp+80h] [rbp-19h]
  __int64 v20; // [rsp+88h] [rbp-11h]
  int *v21; // [rsp+90h] [rbp-9h]
  __int64 v22; // [rsp+98h] [rbp-1h]
  int *v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]
  const unsigned __int16 *v25; // [rsp+B0h] [rbp+17h]
  int v26; // [rsp+B8h] [rbp+1Fh]
  int v27; // [rsp+BCh] [rbp+23h]

  v5 = a3;
  if ( (unsigned int)dword_140023000 > 5
    && (qword_140023010 & 0x400000000000LL) != 0
    && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
  {
    v7 = (const unsigned __int16 *)((char *)this + 16);
    v10 = a4;
    v11 = a3;
    v12 = a2;
    v13 = 0x2000000;
    if ( this == (COmaDmPrcLogger *)-16LL )
    {
      v7 = &qword_14001A560;
      v9 = 1;
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( *((_BYTE *)v7 + v8) );
      v9 = v8 + 1;
    }
    v25 = v7;
    v26 = v9;
    v23 = &v10;
    v27 = 0;
    v21 = &v11;
    v24 = 4;
    v19 = &v12;
    v22 = 4;
    v17 = &v13;
    v20 = 4;
    v18 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, (unsigned __int8 *)&word_14001DB6E, 0, 0, 7u, &v14);
  }
  if ( (byte_1400242C1 & 4) != 0 )
  {
    v10 = a4;
    v15 = &v12;
    v11 = v5;
    v17 = (__int64 *)&v11;
    v12 = a2;
    v19 = &v10;
    v16 = 4;
    v18 = 4;
    v20 = 4;
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmWvdSessionInitialization,
      a3,
      4u,
      &v14);
  }
}

```

## disassembly

```asm
0x14000cbf8  push    rbp
0x14000cbfa  push    rbx
0x14000cbfb  push    rsi
0x14000cbfc  push    rdi
0x14000cbfd  push    r15
0x14000cbff  lea     rbp, [rsp-37h]
0x14000cc04  sub     rsp, 0D0h
0x14000cc0b  mov     rax, cs:__security_cookie
0x14000cc12  xor     rax, rsp
0x14000cc15  mov     [rbp+57h+var_30], rax
0x14000cc19  mov     eax, cs:dword_140023000
0x14000cc1f  mov     ebx, r9d
0x14000cc22  mov     edi, r8d
0x14000cc25  mov     esi, edx
0x14000cc27  mov     r15d, 4
0x14000cc2d  cmp     eax, 5
0x14000cc30  jbe     loc_14000CD0A
0x14000cc36  mov     r10, cs:qword_140023018
0x14000cc3d  mov     rdx, 400000000000h
0x14000cc47  mov     rax, cs:qword_140023010
0x14000cc4e  test    rdx, rax
0x14000cc51  jz      loc_14000CD0A
0x14000cc57  mov     rax, r10
0x14000cc5a  and     rax, rdx
0x14000cc5d  cmp     rax, r10
0x14000cc60  jnz     loc_14000CD0A
0x14000cc66  lea     rax, [rcx+10h]
0x14000cc6a  mov     [rbp+57h+var_C0], ebx
0x14000cc6d  mov     [rbp+57h+var_B8], r8d
0x14000cc71  mov     [rbp+57h+var_B0], esi
0x14000cc74  mov     [rbp+57h+var_A8], 2000000h
0x14000cc7c  test    rax, rax
0x14000cc7f  jz      short loc_14000CC92
0x14000cc81  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000cc85  inc     rcx
0x14000cc88  cmp     byte ptr [rax+rcx], 0
0x14000cc8c  jnz     short loc_14000CC85
0x14000cc8e  inc     ecx
0x14000cc90  jmp     short loc_14000CC9E
0x14000cc92  lea     rax, qword_14001A560
0x14000cc99  mov     ecx, 1
0x14000cc9e  mov     [rbp+57h+var_40], rax
0x14000cca2  lea     rdx, word_14001DB6E
0x14000cca9  lea     rax, [rbp+57h+var_C0]
0x14000ccad  mov     [rbp+57h+var_38], ecx
0x14000ccb0  mov     [rbp+57h+var_50], rax
0x14000ccb4  lea     rcx, dword_140023000
0x14000ccbb  lea     rax, [rbp+57h+var_B8]
0x14000ccbf  mov     [rbp+57h+var_34], 0
0x14000ccc6  mov     [rbp+57h+var_60], rax
0x14000ccca  xor     r9d, r9d
0x14000cccd  lea     rax, [rbp+57h+var_B0]
0x14000ccd1  mov     [rbp+57h+var_48], r15
0x14000ccd5  mov     [rbp+57h+var_70], rax
0x14000ccd9  xor     r8d, r8d
0x14000ccdc  lea     rax, [rbp+57h+var_A8]
0x14000cce0  mov     [rbp+57h+var_58], r15
0x14000cce4  mov     [rbp+57h+var_80], rax
0x14000cce8  lea     rax, [rbp+57h+var_A0]
0x14000ccec  mov     [rsp+0F0h+var_C8], rax
0x14000ccf1  mov     dword ptr [rsp+0F0h+var_D0], 7
0x14000ccf9  mov     [rbp+57h+var_68], r15
0x14000ccfd  mov     [rbp+57h+var_78], 8
0x14000cd05  call    _tlgWriteTransfer_EventWriteTransfer
0x14000cd0a  test    cs:byte_1400242C1, r15b
0x14000cd11  jz      short loc_14000CD58
0x14000cd13  lea     rax, [rbp+57h+var_B0]
0x14000cd17  mov     [rbp+57h+var_C0], ebx
0x14000cd1a  mov     [rbp+57h+var_90], rax
0x14000cd1e  lea     rdx, EnterpriseDiagnosticsOmaDmWvdSessionInitialization
0x14000cd25  lea     rax, [rbp+57h+var_B8]
0x14000cd29  mov     [rbp+57h+var_B8], edi
0x14000cd2c  mov     [rbp+57h+var_80], rax
0x14000cd30  mov     r9d, r15d
0x14000cd33  lea     rax, [rbp+57h+var_C0]
0x14000cd37  mov     [rbp+57h+var_B0], esi
0x14000cd3a  mov     [rbp+57h+var_70], rax
0x14000cd3e  lea     rax, [rbp+57h+var_A0]
0x14000cd42  mov     [rsp+0F0h+var_D0], rax
0x14000cd47  mov     [rbp+57h+var_88], r15
0x14000cd4b  mov     [rbp+57h+var_78], r15
0x14000cd4f  mov     [rbp+57h+var_68], r15
0x14000cd53  call    McGenEventWrite_EventWriteTransfer
0x14000cd58  mov     rcx, [rbp+57h+var_30]
0x14000cd5c  xor     rcx, rsp; StackCookie
0x14000cd5f  call    __security_check_cookie
0x14000cd64  add     rsp, 0D0h
0x14000cd6b  pop     r15
0x14000cd6d  pop     rdi
0x14000cd6e  pop     rsi
0x14000cd6f  pop     rbx
0x14000cd70  pop     rbp
0x14000cd71  retn
```
