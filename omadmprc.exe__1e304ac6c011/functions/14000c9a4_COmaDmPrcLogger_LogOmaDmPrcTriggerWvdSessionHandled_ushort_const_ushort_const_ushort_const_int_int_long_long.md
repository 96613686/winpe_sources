# COmaDmPrcLogger::LogOmaDmPrcTriggerWvdSessionHandled(ushort const *,ushort const *,ushort const *,int,int,long,long)

- ea: `0x14000c9a4`
- end: `0x14000cbef`
- name: `?LogOmaDmPrcTriggerWvdSessionHandled@COmaDmPrcLogger@@QEAAXPEBG00HHJJ@Z`
- size: `587`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f13c`

## callees

- `0x140001090`
- `0x14000c9a4`
- `0x14000d108`
- `0x140015690`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcTriggerWvdSessionHandled(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        int a8)
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
  bool v24; // [rsp+50h] [rbp-B0h] BYREF
  bool v25; // [rsp+51h] [rbp-AFh] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 *v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+ACh] [rbp-54h]
  __int64 *v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+B8h] [rbp-48h]
  int v37; // [rsp+BCh] [rbp-44h]
  __int64 *v38; // [rsp+C0h] [rbp-40h]
  int v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+CCh] [rbp-34h]
  bool *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  bool *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  int *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  int *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v49; // [rsp+110h] [rbp+10h]
  int v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+11Ch] [rbp+1Ch]

  v11 = this;
  if ( (unsigned int)dword_140023000 > 5 )
  {
    LODWORD(this) = qword_140023018;
    if ( (qword_140023010 & 0x400000000000LL) != 0 && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
    {
      v26 = a8;
      v27 = a7;
      v12 = (const unsigned __int16 *)((char *)v11 + 16);
      v28 = 0x2000000;
      v24 = a6 > 0;
      v25 = a5 > 0;
      v13 = -1;
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
      v49 = v12;
      v47 = &v26;
      v45 = &v27;
      v43 = &v24;
      v44 = 1;
      v16 = &qword_14001A798;
      v42 = 1;
      v17 = 2;
      v41 = &v25;
      v50 = v15;
      v51 = 0;
      v48 = 4;
      v46 = 4;
      if ( a4 )
      {
        v18 = (__int64 *)a4;
        v19 = -1;
        do
          ++v19;
        while ( a4[v19] );
        v20 = 2 * v19 + 2;
      }
      else
      {
        v18 = &qword_14001A798;
        v20 = 2;
      }
      v38 = v18;
      v39 = v20;
      v40 = 0;
      if ( a3 )
      {
        v21 = (__int64 *)a3;
        v22 = -1;
        do
          ++v22;
        while ( a3[v22] );
        v23 = 2 * v22 + 2;
      }
      else
      {
        v21 = &qword_14001A798;
        v23 = 2;
      }
      v35 = v21;
      v36 = v23;
      v37 = 0;
      if ( a2 )
      {
        v16 = (__int64 *)a2;
        do
          ++v13;
        while ( a2[v13] );
        v17 = 2 * v13 + 2;
      }
      v32 = v16;
      v30 = &v28;
      v33 = v17;
      v34 = 0;
      v31 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_140023000,
        (unsigned __int8 *)byte_14001DC25,
        0,
        0,
        0xBu,
        &v29);
    }
  }
  if ( (byte_1400242C1 & 4) != 0 )
    McTemplateU0zzzqqdd_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)v11,
      (_DWORD)a2,
      (_DWORD)a3,
      (__int64)a4,
      a5,
      a6,
      a7,
      a8);
}

```

## disassembly

```asm
0x14000c9a4  mov     [rsp-8+arg_0], rbx
0x14000c9a9  push    rbp
0x14000c9aa  push    rsi
0x14000c9ab  push    rdi
0x14000c9ac  push    r12
0x14000c9ae  push    r13
0x14000c9b0  push    r14
0x14000c9b2  push    r15
0x14000c9b4  lea     rbp, [rsp-30h]
0x14000c9b9  sub     rsp, 130h
0x14000c9c0  mov     rax, cs:__security_cookie
0x14000c9c7  xor     rax, rsp
0x14000c9ca  mov     [rbp+60h+var_40], rax
0x14000c9ce  mov     eax, cs:dword_140023000
0x14000c9d4  mov     rbx, rdx
0x14000c9d7  mov     r14d, [rbp+60h+arg_38]
0x14000c9de  mov     rsi, r9
0x14000c9e1  mov     r15d, [rbp+60h+arg_30]
0x14000c9e8  mov     rdi, r8
0x14000c9eb  mov     r12d, [rbp+60h+arg_28]
0x14000c9f2  mov     rdx, rcx
0x14000c9f5  mov     r13d, [rbp+60h+arg_20]
0x14000c9fc  cmp     eax, 5
0x14000c9ff  jbe     loc_14000CB9A
0x14000ca05  mov     rcx, cs:qword_140023018
0x14000ca0c  mov     r8, 400000000000h
0x14000ca16  mov     rax, cs:qword_140023010
0x14000ca1d  test    r8, rax
0x14000ca20  jz      loc_14000CB9A
0x14000ca26  mov     rax, rcx
0x14000ca29  and     rax, r8
0x14000ca2c  cmp     rax, rcx
0x14000ca2f  jnz     loc_14000CB9A
0x14000ca35  xor     r10d, r10d
0x14000ca38  mov     [rsp+160h+var_10C], r14d
0x14000ca3d  test    r12d, r12d
0x14000ca40  mov     [rsp+160h+var_108], r15d
0x14000ca45  lea     rax, [rdx+10h]
0x14000ca49  mov     [rsp+160h+var_100], 2000000h
0x14000ca52  setnle  [rsp+160h+var_110]
0x14000ca57  test    r13d, r13d
0x14000ca5a  lea     r8d, [r10+1]
0x14000ca5e  setnle  [rsp+160h+var_10F]
0x14000ca63  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000ca67  test    rax, rax
0x14000ca6a  jz      short loc_14000CA7C
0x14000ca6c  mov     rcx, rdx
0x14000ca6f  inc     rcx
0x14000ca72  cmp     [rax+rcx], r10b
0x14000ca76  jnz     short loc_14000CA6F
0x14000ca78  inc     ecx
0x14000ca7a  jmp     short loc_14000CA86
0x14000ca7c  lea     rax, qword_14001A560
0x14000ca83  mov     ecx, r8d
0x14000ca86  mov     [rbp+60h+var_50], rax
0x14000ca8a  lea     rax, [rsp+160h+var_10C]
0x14000ca8f  mov     [rbp+60h+var_60], rax
0x14000ca93  lea     rax, [rsp+160h+var_108]
0x14000ca98  mov     [rbp+60h+var_70], rax
0x14000ca9c  lea     rax, [rsp+160h+var_110]
0x14000caa1  mov     [rbp+60h+var_80], rax
0x14000caa5  lea     rax, [rsp+160h+var_10F]
0x14000caaa  mov     [rbp+60h+var_78], r8
0x14000caae  lea     r9, qword_14001A798
0x14000cab5  mov     [rbp+60h+var_88], r8
0x14000cab9  mov     r8d, 2
0x14000cabf  mov     [rbp+60h+var_90], rax
0x14000cac3  mov     [rbp+60h+var_48], ecx
0x14000cac6  mov     [rbp+60h+var_44], r10d
0x14000caca  mov     [rbp+60h+var_58], 4
0x14000cad2  mov     [rbp+60h+var_68], 4
0x14000cada  test    rsi, rsi
0x14000cadd  jz      short loc_14000CAF8
0x14000cadf  mov     rcx, rsi
0x14000cae2  mov     rax, rdx
0x14000cae5  inc     rax
0x14000cae8  cmp     [rsi+rax*2], r10w
0x14000caed  jnz     short loc_14000CAE5
0x14000caef  lea     eax, ds:2[rax*2]
0x14000caf6  jmp     short loc_14000CAFE
0x14000caf8  mov     rcx, r9
0x14000cafb  mov     eax, r8d
0x14000cafe  mov     [rbp+60h+var_A0], rcx
0x14000cb02  mov     [rbp+60h+var_98], eax
0x14000cb05  mov     [rbp+60h+var_94], r10d
0x14000cb09  test    rdi, rdi
0x14000cb0c  jz      short loc_14000CB27
0x14000cb0e  mov     rcx, rdi
0x14000cb11  mov     rax, rdx
0x14000cb14  inc     rax
0x14000cb17  cmp     [rdi+rax*2], r10w
0x14000cb1c  jnz     short loc_14000CB14
0x14000cb1e  lea     eax, ds:2[rax*2]
0x14000cb25  jmp     short loc_14000CB2D
0x14000cb27  mov     rcx, r9
0x14000cb2a  mov     eax, r8d
0x14000cb2d  mov     [rbp+60h+var_B0], rcx
0x14000cb31  mov     [rbp+60h+var_A8], eax
0x14000cb34  mov     [rbp+60h+var_A4], r10d
0x14000cb38  test    rbx, rbx
0x14000cb3b  jz      short loc_14000CB52
0x14000cb3d  mov     r9, rbx
0x14000cb40  inc     rdx
0x14000cb43  cmp     [rbx+rdx*2], r10w
0x14000cb48  jnz     short loc_14000CB40
0x14000cb4a  lea     r8d, ds:2[rdx*2]
0x14000cb52  lea     rax, [rsp+160h+var_100]
0x14000cb57  mov     [rbp+60h+var_C0], r9
0x14000cb5b  mov     [rbp+60h+var_D0], rax
0x14000cb5f  lea     rdx, byte_14001DC25
0x14000cb66  lea     rax, [rsp+160h+var_F0]
0x14000cb6b  mov     [rbp+60h+var_B8], r8d
0x14000cb6f  mov     [rsp+160h+var_138], rax
0x14000cb74  lea     rcx, dword_140023000
0x14000cb7b  xor     r9d, r9d
0x14000cb7e  mov     dword ptr [rsp+160h+var_140], 0Bh
0x14000cb86  xor     r8d, r8d
0x14000cb89  mov     [rbp+60h+var_B4], r10d
0x14000cb8d  mov     [rbp+60h+var_C8], 8
0x14000cb95  call    _tlgWriteTransfer_EventWriteTransfer
0x14000cb9a  test    cs:byte_1400242C1, 4
0x14000cba1  jz      short loc_14000CBC7
0x14000cba3  mov     [rsp+160h+var_120], r14d
0x14000cba8  mov     r9, rdi
0x14000cbab  mov     [rsp+160h+var_128], r15d
0x14000cbb0  mov     r8, rbx
0x14000cbb3  mov     [rsp+160h+var_130], r12d
0x14000cbb8  mov     dword ptr [rsp+160h+var_138], r13d
0x14000cbbd  mov     [rsp+160h+var_140], rsi
0x14000cbc2  call    McTemplateU0zzzqqdd_EventWriteTransfer
0x14000cbc7  mov     rcx, [rbp+60h+var_40]
0x14000cbcb  xor     rcx, rsp; StackCookie
0x14000cbce  call    __security_check_cookie
0x14000cbd3  mov     rbx, [rsp+160h+arg_0]
0x14000cbdb  add     rsp, 130h
0x14000cbe2  pop     r15
0x14000cbe4  pop     r14
0x14000cbe6  pop     r13
0x14000cbe8  pop     r12
0x14000cbea  pop     rdi
0x14000cbeb  pop     rsi
0x14000cbec  pop     rbp
0x14000cbed  retn
```
