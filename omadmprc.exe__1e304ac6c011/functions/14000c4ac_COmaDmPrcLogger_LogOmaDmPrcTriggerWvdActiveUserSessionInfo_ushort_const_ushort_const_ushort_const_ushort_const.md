# COmaDmPrcLogger::LogOmaDmPrcTriggerWvdActiveUserSessionInfo(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong)

- ea: `0x14000c4ac`
- end: `0x14000c710`
- name: `?LogOmaDmPrcTriggerWvdActiveUserSessionInfo@COmaDmPrcLogger@@QEAAXPEBG000KKK@Z`
- size: `612`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013350`

## callees

- `0x140001090`
- `0x14000c4ac`
- `0x14000d380`
- `0x140015690`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcTriggerWvdActiveUserSessionInfo(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  COmaDmPrcLogger *v11; // rdx
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // ecx
  __int64 *v16; // r9
  int v17; // r8d
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+ACh] [rbp-54h]
  __int64 *v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+BCh] [rbp-44h]
  __int64 *v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+CCh] [rbp-34h]
  __int64 *v43; // [rsp+D0h] [rbp-30h]
  int v44; // [rsp+D8h] [rbp-28h]
  int v45; // [rsp+DCh] [rbp-24h]
  unsigned int *v46; // [rsp+E0h] [rbp-20h]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  unsigned int *v48; // [rsp+F0h] [rbp-10h]
  __int64 v49; // [rsp+F8h] [rbp-8h]
  unsigned int *v50; // [rsp+100h] [rbp+0h]
  __int64 v51; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v52; // [rsp+110h] [rbp+10h]
  int v53; // [rsp+118h] [rbp+18h]
  int v54; // [rsp+11Ch] [rbp+1Ch]

  v11 = this;
  if ( (unsigned int)dword_140023000 > 5 )
  {
    LODWORD(this) = qword_140023018;
    if ( (qword_140023010 & 0x400000000000LL) != 0 && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
    {
      v12 = (const unsigned __int16 *)((char *)v11 + 16);
      v27 = a8;
      v13 = -1;
      v28 = a7;
      v29 = a6;
      v30 = 0x2000000;
      if ( v12 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_BYTE *)v12 + v14) );
        v15 = v14 + 1;
      }
      else
      {
        v12 = &qword_14001A560;
        v15 = 1;
      }
      v52 = v12;
      v50 = &v27;
      v48 = &v28;
      v46 = &v29;
      v16 = &qword_14001A798;
      v53 = v15;
      v17 = 2;
      v54 = 0;
      v51 = 4;
      v49 = 4;
      v47 = 4;
      if ( a5 )
      {
        v18 = (__int64 *)a5;
        v19 = -1;
        do
          ++v19;
        while ( a5[v19] );
        v20 = 2 * v19 + 2;
      }
      else
      {
        v18 = &qword_14001A798;
        v20 = 2;
      }
      v43 = v18;
      v44 = v20;
      v45 = 0;
      if ( a4 )
      {
        v21 = (__int64 *)a4;
        v22 = -1;
        do
          ++v22;
        while ( a4[v22] );
        v23 = 2 * v22 + 2;
      }
      else
      {
        v21 = &qword_14001A798;
        v23 = 2;
      }
      v40 = v21;
      v41 = v23;
      v42 = 0;
      if ( a3 )
      {
        v24 = (__int64 *)a3;
        v25 = -1;
        do
          ++v25;
        while ( a3[v25] );
        v26 = 2 * v25 + 2;
      }
      else
      {
        v24 = &qword_14001A798;
        v26 = 2;
      }
      v37 = v24;
      v38 = v26;
      v39 = 0;
      if ( a2 )
      {
        v16 = (__int64 *)a2;
        do
          ++v13;
        while ( a2[v13] );
        v17 = 2 * v13 + 2;
      }
      v34 = v16;
      v32 = &v30;
      v35 = v17;
      v36 = 0;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_140023000,
        (unsigned __int8 *)byte_14001DDA3,
        0,
        0,
        0xBu,
        &v31);
    }
  }
  if ( (byte_1400242C1 & 4) != 0 )
    McTemplateU0zzzzqqq_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)v11,
      (_DWORD)a2,
      (_DWORD)a3,
      (__int64)a4,
      (__int64)a5,
      a6,
      a7,
      a8);
}

```

## disassembly

```asm
0x14000c4ac  mov     [rsp-8+arg_0], rbx
0x14000c4b1  push    rbp
0x14000c4b2  push    rsi
0x14000c4b3  push    rdi
0x14000c4b4  push    r12
0x14000c4b6  push    r13
0x14000c4b8  push    r14
0x14000c4ba  push    r15
0x14000c4bc  lea     rbp, [rsp-30h]
0x14000c4c1  sub     rsp, 130h
0x14000c4c8  mov     rax, cs:__security_cookie
0x14000c4cf  xor     rax, rsp
0x14000c4d2  mov     [rbp+60h+var_40], rax
0x14000c4d6  mov     eax, cs:dword_140023000
0x14000c4dc  mov     rbx, rdx
0x14000c4df  mov     r14, [rbp+60h+arg_20]
0x14000c4e6  mov     rsi, r9
0x14000c4e9  mov     r15d, [rbp+60h+arg_38]
0x14000c4f0  mov     rdi, r8
0x14000c4f3  mov     r12d, [rbp+60h+arg_30]
0x14000c4fa  mov     rdx, rcx
0x14000c4fd  mov     r13d, [rbp+60h+arg_28]
0x14000c504  cmp     eax, 5
0x14000c507  jbe     loc_14000C6BB
0x14000c50d  mov     rcx, cs:qword_140023018
0x14000c514  mov     r8, 400000000000h
0x14000c51e  mov     rax, cs:qword_140023010
0x14000c525  test    r8, rax
0x14000c528  jz      loc_14000C6BB
0x14000c52e  mov     rax, rcx
0x14000c531  and     rax, r8
0x14000c534  cmp     rax, rcx
0x14000c537  jnz     loc_14000C6BB
0x14000c53d  lea     rax, [rdx+10h]
0x14000c541  mov     [rsp+160h+var_110], r15d
0x14000c546  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000c54a  mov     [rsp+160h+var_10C], r12d
0x14000c54f  xor     r10d, r10d
0x14000c552  mov     [rsp+160h+var_108], r13d
0x14000c557  mov     [rsp+160h+var_100], 2000000h
0x14000c560  test    rax, rax
0x14000c563  jz      short loc_14000C575
0x14000c565  mov     rcx, rdx
0x14000c568  inc     rcx
0x14000c56b  cmp     [rax+rcx], r10b
0x14000c56f  jnz     short loc_14000C568
0x14000c571  inc     ecx
0x14000c573  jmp     short loc_14000C581
0x14000c575  lea     rax, qword_14001A560
0x14000c57c  mov     ecx, 1
0x14000c581  mov     [rbp+60h+var_50], rax
0x14000c585  lea     rax, [rsp+160h+var_110]
0x14000c58a  mov     [rbp+60h+var_60], rax
0x14000c58e  lea     rax, [rsp+160h+var_10C]
0x14000c593  mov     [rbp+60h+var_70], rax
0x14000c597  lea     rax, [rsp+160h+var_108]
0x14000c59c  mov     [rbp+60h+var_80], rax
0x14000c5a0  lea     r9, qword_14001A798
0x14000c5a7  mov     [rbp+60h+var_48], ecx
0x14000c5aa  mov     r8d, 2
0x14000c5b0  mov     [rbp+60h+var_44], r10d
0x14000c5b4  mov     [rbp+60h+var_58], 4
0x14000c5bc  mov     [rbp+60h+var_68], 4
0x14000c5c4  mov     [rbp+60h+var_78], 4
0x14000c5cc  test    r14, r14
0x14000c5cf  jz      short loc_14000C5EA
0x14000c5d1  mov     rcx, r14
0x14000c5d4  mov     rax, rdx
0x14000c5d7  inc     rax
0x14000c5da  cmp     [r14+rax*2], r10w
0x14000c5df  jnz     short loc_14000C5D7
0x14000c5e1  lea     eax, ds:2[rax*2]
0x14000c5e8  jmp     short loc_14000C5F0
0x14000c5ea  mov     rcx, r9
0x14000c5ed  mov     eax, r8d
0x14000c5f0  mov     [rbp+60h+var_90], rcx
0x14000c5f4  mov     [rbp+60h+var_88], eax
0x14000c5f7  mov     [rbp+60h+var_84], r10d
0x14000c5fb  test    rsi, rsi
0x14000c5fe  jz      short loc_14000C619
0x14000c600  mov     rcx, rsi
0x14000c603  mov     rax, rdx
0x14000c606  inc     rax
0x14000c609  cmp     [rsi+rax*2], r10w
0x14000c60e  jnz     short loc_14000C606
0x14000c610  lea     eax, ds:2[rax*2]
0x14000c617  jmp     short loc_14000C61F
0x14000c619  mov     rcx, r9
0x14000c61c  mov     eax, r8d
0x14000c61f  mov     [rbp+60h+var_A0], rcx
0x14000c623  mov     [rbp+60h+var_98], eax
0x14000c626  mov     [rbp+60h+var_94], r10d
0x14000c62a  test    rdi, rdi
0x14000c62d  jz      short loc_14000C648
0x14000c62f  mov     rcx, rdi
0x14000c632  mov     rax, rdx
0x14000c635  inc     rax
0x14000c638  cmp     [rdi+rax*2], r10w
0x14000c63d  jnz     short loc_14000C635
0x14000c63f  lea     eax, ds:2[rax*2]
0x14000c646  jmp     short loc_14000C64E
0x14000c648  mov     rcx, r9
0x14000c64b  mov     eax, r8d
0x14000c64e  mov     [rbp+60h+var_B0], rcx
0x14000c652  mov     [rbp+60h+var_A8], eax
0x14000c655  mov     [rbp+60h+var_A4], r10d
0x14000c659  test    rbx, rbx
0x14000c65c  jz      short loc_14000C673
0x14000c65e  mov     r9, rbx
0x14000c661  inc     rdx
0x14000c664  cmp     [rbx+rdx*2], r10w
0x14000c669  jnz     short loc_14000C661
0x14000c66b  lea     r8d, ds:2[rdx*2]
0x14000c673  lea     rax, [rsp+160h+var_100]
0x14000c678  mov     [rbp+60h+var_C0], r9
0x14000c67c  mov     [rbp+60h+var_D0], rax
0x14000c680  lea     rdx, byte_14001DDA3
0x14000c687  lea     rax, [rsp+160h+var_F0]
0x14000c68c  mov     [rbp+60h+var_B8], r8d
0x14000c690  mov     [rsp+160h+var_138], rax
0x14000c695  lea     rcx, dword_140023000
0x14000c69c  xor     r9d, r9d
0x14000c69f  mov     dword ptr [rsp+160h+var_140], 0Bh
0x14000c6a7  xor     r8d, r8d
0x14000c6aa  mov     [rbp+60h+var_B4], r10d
0x14000c6ae  mov     [rbp+60h+var_C8], 8
0x14000c6b6  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c6bb  test    cs:byte_1400242C1, 4
0x14000c6c2  jz      short loc_14000C6E8
0x14000c6c4  mov     [rsp+160h+var_120], r15d
0x14000c6c9  mov     r9, rdi
0x14000c6cc  mov     [rsp+160h+var_128], r12d
0x14000c6d1  mov     r8, rbx
0x14000c6d4  mov     [rsp+160h+var_130], r13d
0x14000c6d9  mov     [rsp+160h+var_138], r14
0x14000c6de  mov     [rsp+160h+var_140], rsi
0x14000c6e3  call    McTemplateU0zzzzqqq_EventWriteTransfer
0x14000c6e8  mov     rcx, [rbp+60h+var_40]
0x14000c6ec  xor     rcx, rsp; StackCookie
0x14000c6ef  call    __security_check_cookie
0x14000c6f4  mov     rbx, [rsp+160h+arg_0]
0x14000c6fc  add     rsp, 130h
0x14000c703  pop     r15
0x14000c705  pop     r14
0x14000c707  pop     r13
0x14000c709  pop     r12
0x14000c70b  pop     rdi
0x14000c70c  pop     rsi
0x14000c70d  pop     rbp
0x14000c70e  retn
```
