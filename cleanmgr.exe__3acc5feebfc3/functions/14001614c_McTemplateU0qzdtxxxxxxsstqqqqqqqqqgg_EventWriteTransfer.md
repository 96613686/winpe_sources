# McTemplateU0qzdtxxxxxxsstqqqqqqqqqgg_EventWriteTransfer

- ea: `0x14001614c`
- end: `0x140016412`
- name: `McTemplateU0qzdtxxxxxxsstqqqqqqqqqgg_EventWriteTransfer`
- size: `710`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, char, char, char, char, char, char, char, const char *, const char *, char, char, char, char, char, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010be4`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x14001614c`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzdtxxxxxxsstqqqqqqqqqgg_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        const char *a13,
        const char *a14,
        char a15,
        char a16,
        char a17,
        char a18,
        char a19,
        char a20,
        char a21,
        char a22,
        char a23,
        char a24,
        char a25,
        char a26)
{
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // ecx
  __int64 v29; // r8
  const char *v30; // rcx
  __int64 v31; // rdx
  int v32; // edx
  const char *v33; // rcx
  bool v34; // zf
  int v36; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+40h] [rbp-C0h] BYREF
  int *v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+58h] [rbp-A8h]
  const wchar_t *v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+68h] [rbp-98h]
  int v42; // [rsp+6Ch] [rbp-94h]
  char *v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+78h] [rbp-88h]
  char *v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  char *v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  char *v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  char *v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  char *v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  char *v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  char *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  const char *v59; // [rsp+F0h] [rbp-10h]
  int v60; // [rsp+F8h] [rbp-8h]
  int v61; // [rsp+FCh] [rbp-4h]
  const char *v62; // [rsp+100h] [rbp+0h]
  int v63; // [rsp+108h] [rbp+8h]
  int v64; // [rsp+10Ch] [rbp+Ch]
  char *v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  char *v67; // [rsp+120h] [rbp+20h]
  __int64 v68; // [rsp+128h] [rbp+28h]
  char *v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h]
  char *v71; // [rsp+140h] [rbp+40h]
  __int64 v72; // [rsp+148h] [rbp+48h]
  char *v73; // [rsp+150h] [rbp+50h]
  __int64 v74; // [rsp+158h] [rbp+58h]
  char *v75; // [rsp+160h] [rbp+60h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  char *v77; // [rsp+170h] [rbp+70h]
  __int64 v78; // [rsp+178h] [rbp+78h]
  char *v79; // [rsp+180h] [rbp+80h]
  __int64 v80; // [rsp+188h] [rbp+88h]
  char *v81; // [rsp+190h] [rbp+90h]
  __int64 v82; // [rsp+198h] [rbp+98h]
  char *v83; // [rsp+1A0h] [rbp+A0h]
  __int64 v84; // [rsp+1A8h] [rbp+A8h]
  char *v85; // [rsp+1B0h] [rbp+B0h]
  __int64 v86; // [rsp+1B8h] [rbp+B8h]
  char *v87; // [rsp+1C0h] [rbp+C0h]
  __int64 v88; // [rsp+1C8h] [rbp+C8h]

  v36 = 2;
  v38 = &v36;
  v26 = -1;
  v39 = 4;
  if ( a4 )
  {
    v27 = -1;
    do
      ++v27;
    while ( a4[v27] );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v28 = 10;
  }
  v41 = v28;
  v42 = 0;
  v43 = &a5;
  v44 = 4;
  v45 = &a6;
  if ( !a4 )
    a4 = L"NULL";
  v40 = a4;
  v47 = &a7;
  v29 = 5;
  v46 = 4;
  v49 = &a8;
  v51 = &a9;
  v53 = &a10;
  v55 = &a11;
  v57 = &a12;
  v30 = a13;
  v48 = 8;
  v50 = 8;
  v52 = 8;
  v54 = 8;
  v56 = 8;
  v58 = 8;
  if ( a13 )
  {
    v31 = -1;
    do
      ++v31;
    while ( a13[v31] );
    v32 = v31 + 1;
  }
  else
  {
    v32 = 5;
  }
  v60 = v32;
  v61 = 0;
  if ( !a13 )
    v30 = "NULL";
  v59 = v30;
  v33 = a14;
  v34 = a14 == 0;
  if ( a14 )
  {
    do
      ++v26;
    while ( a14[v26] );
    v29 = (unsigned int)(v26 + 1);
    v34 = a14 == 0;
  }
  v63 = v29;
  v65 = &a15;
  v64 = 0;
  v67 = &a16;
  if ( v34 )
    v33 = "NULL";
  v62 = v33;
  v69 = &a17;
  v66 = 4;
  v71 = &a18;
  v73 = &a19;
  v75 = &a20;
  v77 = &a21;
  v79 = &a22;
  v81 = &a23;
  v83 = &a24;
  v85 = &a25;
  v87 = &a26;
  v68 = 4;
  v70 = 4;
  v72 = 4;
  v74 = 4;
  v76 = 4;
  v78 = 4;
  v80 = 4;
  v82 = 4;
  v84 = 4;
  v86 = 8;
  v88 = 8;
  return McGenEventWrite_EventWriteTransfer((__int64)v33, (const EVENT_DESCRIPTOR *)CleanmgrPurge, v29, 0x19u, &v37);
}

```

## disassembly

```asm
0x14001614c  mov     [rsp-8+arg_0], rbx
0x140016151  push    rbp
0x140016152  lea     rbp, [rsp-0E0h]
0x14001615a  sub     rsp, 1E0h
0x140016161  mov     rax, cs:__security_cookie
0x140016168  xor     rax, rsp
0x14001616b  mov     [rbp+0E0h+var_10], rax
0x140016172  lea     rax, [rsp+1E0h+var_1B0]
0x140016177  mov     [rsp+1E0h+var_1B0], 2
0x14001617f  mov     [rsp+1E0h+var_190], rax
0x140016184  xor     r10d, r10d
0x140016187  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001618b  mov     [rsp+1E0h+var_188], 4
0x140016194  test    r9, r9
0x140016197  jz      short loc_1400161AF
0x140016199  mov     rcx, rax
0x14001619c  inc     rcx
0x14001619f  cmp     [r9+rcx*2], r10w
0x1400161a4  jnz     short loc_14001619C
0x1400161a6  lea     ecx, ds:2[rcx*2]
0x1400161ad  jmp     short loc_1400161B4
0x1400161af  mov     ecx, 0Ah
0x1400161b4  mov     [rsp+1E0h+var_178], ecx
0x1400161b8  lea     rdx, aNull_0; "NULL"
0x1400161bf  lea     rcx, [rbp+0E0h+arg_20]
0x1400161c6  mov     [rsp+1E0h+var_174], r10d
0x1400161cb  mov     [rsp+1E0h+var_170], rcx
0x1400161d0  test    r9, r9
0x1400161d3  lea     rcx, [rbp+0E0h+arg_28]
0x1400161da  mov     [rsp+1E0h+var_168], 4
0x1400161e3  mov     [rbp+0E0h+var_160], rcx
0x1400161e7  cmovz   r9, rdx
0x1400161eb  lea     rcx, [rbp+0E0h+arg_30]
0x1400161f2  mov     [rsp+1E0h+var_180], r9
0x1400161f7  mov     [rbp+0E0h+var_150], rcx
0x1400161fb  mov     r8d, 5
0x140016201  lea     rcx, [rbp+0E0h+arg_38]
0x140016208  mov     [rbp+0E0h+var_158], 4
0x140016210  mov     [rbp+0E0h+var_140], rcx
0x140016214  lea     rcx, [rbp+0E0h+arg_40]
0x14001621b  mov     [rbp+0E0h+var_130], rcx
0x14001621f  lea     rcx, [rbp+0E0h+arg_48]
0x140016226  mov     [rbp+0E0h+var_120], rcx
0x14001622a  lea     rcx, [rbp+0E0h+arg_50]
0x140016231  mov     [rbp+0E0h+var_110], rcx
0x140016235  lea     rcx, [rbp+0E0h+arg_58]
0x14001623c  mov     [rbp+0E0h+var_100], rcx
0x140016240  mov     rcx, [rbp+0E0h+arg_60]
0x140016247  mov     [rbp+0E0h+var_148], 8
0x14001624f  mov     [rbp+0E0h+var_138], 8
0x140016257  mov     [rbp+0E0h+var_128], 8
0x14001625f  mov     [rbp+0E0h+var_118], 8
0x140016267  mov     [rbp+0E0h+var_108], 8
0x14001626f  mov     [rbp+0E0h+var_F8], 8
0x140016277  test    rcx, rcx
0x14001627a  jz      short loc_14001628C
0x14001627c  mov     rdx, rax
0x14001627f  inc     rdx
0x140016282  cmp     [rcx+rdx], r10b
0x140016286  jnz     short loc_14001627F
0x140016288  inc     edx
0x14001628a  jmp     short loc_14001628F
0x14001628c  mov     edx, r8d
0x14001628f  test    rcx, rcx
0x140016292  mov     [rbp+0E0h+var_E8], edx
0x140016295  lea     rbx, aNull; "NULL"
0x14001629c  mov     [rbp+0E0h+var_E4], r10d
0x1400162a0  cmovz   rcx, rbx
0x1400162a4  mov     [rbp+0E0h+var_F0], rcx
0x1400162a8  mov     rcx, [rbp+0E0h+arg_68]
0x1400162af  test    rcx, rcx
0x1400162b2  jz      short loc_1400162C4
0x1400162b4  inc     rax
0x1400162b7  cmp     [rcx+rax], r10b
0x1400162bb  jnz     short loc_1400162B4
0x1400162bd  lea     r8d, [rax+1]
0x1400162c1  test    rcx, rcx
0x1400162c4  lea     rax, [rbp+0E0h+arg_70]
0x1400162cb  mov     [rbp+0E0h+var_D8], r8d
0x1400162cf  mov     [rbp+0E0h+var_D0], rax
0x1400162d3  lea     rdx, CleanmgrPurge
0x1400162da  lea     rax, [rbp+0E0h+arg_78]
0x1400162e1  mov     [rbp+0E0h+var_D4], r10d
0x1400162e5  mov     [rbp+0E0h+var_C0], rax
0x1400162e9  cmovz   rcx, rbx
0x1400162ed  lea     rax, [rbp+0E0h+arg_80]
0x1400162f4  mov     [rbp+0E0h+var_E0], rcx
0x1400162f8  mov     [rbp+0E0h+var_B0], rax
0x1400162fc  mov     r9d, 19h
0x140016302  lea     rax, [rbp+0E0h+arg_88]
0x140016309  mov     [rbp+0E0h+var_C8], 4
0x140016311  mov     [rbp+0E0h+var_A0], rax
0x140016315  lea     rax, [rbp+0E0h+arg_90]
0x14001631c  mov     [rbp+0E0h+var_90], rax
0x140016320  lea     rax, [rbp+0E0h+arg_98]
0x140016327  mov     [rbp+0E0h+var_80], rax
0x14001632b  lea     rax, [rbp+0E0h+arg_A0]
0x140016332  mov     [rbp+0E0h+var_70], rax
0x140016336  lea     rax, [rbp+0E0h+arg_A8]
0x14001633d  mov     [rbp+0E0h+var_60], rax
0x140016344  lea     rax, [rbp+0E0h+arg_B0]
0x14001634b  mov     [rbp+0E0h+var_50], rax
0x140016352  lea     rax, [rbp+0E0h+arg_B8]
0x140016359  mov     [rbp+0E0h+var_40], rax
0x140016360  lea     rax, [rbp+0E0h+arg_C0]
0x140016367  mov     [rbp+0E0h+var_30], rax
0x14001636e  lea     rax, [rbp+0E0h+arg_C8]
0x140016375  mov     [rbp+0E0h+var_20], rax
0x14001637c  lea     rax, [rsp+1E0h+var_1A0]
0x140016381  mov     [rsp+1E0h+var_1C0], rax
0x140016386  mov     [rbp+0E0h+var_B8], 4
0x14001638e  mov     [rbp+0E0h+var_A8], 4
0x140016396  mov     [rbp+0E0h+var_98], 4
0x14001639e  mov     [rbp+0E0h+var_88], 4
0x1400163a6  mov     [rbp+0E0h+var_78], 4
0x1400163ae  mov     [rbp+0E0h+var_68], 4
0x1400163b6  mov     [rbp+0E0h+var_58], 4
0x1400163c1  mov     [rbp+0E0h+var_48], 4
0x1400163cc  mov     [rbp+0E0h+var_38], 4
0x1400163d7  mov     [rbp+0E0h+var_28], 8
0x1400163e2  mov     [rbp+0E0h+var_18], 8
0x1400163ed  call    McGenEventWrite_EventWriteTransfer
0x1400163f2  mov     rcx, [rbp+0E0h+var_10]
0x1400163f9  xor     rcx, rsp; StackCookie
0x1400163fc  call    __security_check_cookie
0x140016401  mov     rbx, [rsp+1E0h+arg_0]
0x140016409  add     rsp, 1E0h
0x140016410  pop     rbp
0x140016411  retn
```
