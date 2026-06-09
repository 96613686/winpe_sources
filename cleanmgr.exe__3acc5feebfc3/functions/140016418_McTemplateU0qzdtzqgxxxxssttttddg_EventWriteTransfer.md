# McTemplateU0qzdtzqgxxxxssttttddg_EventWriteTransfer

- ea: `0x140016418`
- end: `0x14001669d`
- name: `McTemplateU0qzdtzqgxxxxssttttddg_EventWriteTransfer`
- size: `645`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, char, const wchar_t *, char, char, char, char, char, char, const char *, const char *, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010a00`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x140016418`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzdtzqgxxxxssttttddg_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        const wchar_t *a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        const char *a14,
        const char *a15,
        char a16,
        char a17,
        char a18,
        char a19,
        char a20,
        char a21,
        char a22)
{
  __int64 v22; // rax
  int v23; // r8d
  __int64 v24; // rcx
  int v25; // ecx
  const wchar_t *v26; // rdx
  bool v27; // zf
  __int64 v28; // rcx
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
  const wchar_t *v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+9Ch] [rbp-64h]
  char *v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  char *v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  char *v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  char *v56; // [rsp+D0h] [rbp-30h]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  char *v58; // [rsp+E0h] [rbp-20h]
  __int64 v59; // [rsp+E8h] [rbp-18h]
  char *v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  const char *v62; // [rsp+100h] [rbp+0h]
  int v63; // [rsp+108h] [rbp+8h]
  int v64; // [rsp+10Ch] [rbp+Ch]
  const char *v65; // [rsp+110h] [rbp+10h]
  int v66; // [rsp+118h] [rbp+18h]
  int v67; // [rsp+11Ch] [rbp+1Ch]
  char *v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]
  char *v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+138h] [rbp+38h]
  char *v72; // [rsp+140h] [rbp+40h]
  __int64 v73; // [rsp+148h] [rbp+48h]
  char *v74; // [rsp+150h] [rbp+50h]
  __int64 v75; // [rsp+158h] [rbp+58h]
  char *v76; // [rsp+160h] [rbp+60h]
  __int64 v77; // [rsp+168h] [rbp+68h]
  char *v78; // [rsp+170h] [rbp+70h]
  __int64 v79; // [rsp+178h] [rbp+78h]
  char *v80; // [rsp+180h] [rbp+80h]
  __int64 v81; // [rsp+188h] [rbp+88h]

  v36 = 2;
  v38 = &v36;
  v22 = -1;
  v39 = 4;
  v23 = 10;
  if ( a4 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a4[v24] );
    v25 = 2 * v24 + 2;
  }
  else
  {
    v25 = 10;
  }
  v26 = a7;
  v41 = v25;
  v42 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v43 = &a5;
  v40 = a4;
  v45 = &a6;
  v44 = 4;
  v46 = 4;
  v27 = a7 == 0;
  if ( a7 )
  {
    v28 = -1;
    do
      ++v28;
    while ( a7[v28] );
    v23 = 2 * v28 + 2;
    v27 = a7 == 0;
  }
  v48 = v23;
  v50 = &a8;
  if ( v27 )
    v26 = L"NULL";
  v47 = v26;
  v52 = &a9;
  v29 = 5;
  v49 = 0;
  v54 = &a10;
  v56 = &a11;
  v58 = &a12;
  v60 = &a13;
  v30 = a14;
  v51 = 4;
  v53 = 8;
  v55 = 8;
  v57 = 8;
  v59 = 8;
  v61 = 8;
  if ( a14 )
  {
    v31 = -1;
    do
      ++v31;
    while ( a14[v31] );
    v32 = v31 + 1;
  }
  else
  {
    v32 = 5;
  }
  v63 = v32;
  v64 = 0;
  if ( !a14 )
    v30 = "NULL";
  v62 = v30;
  v33 = a15;
  v34 = a15 == 0;
  if ( a15 )
  {
    do
      ++v22;
    while ( a15[v22] );
    v29 = (unsigned int)(v22 + 1);
    v34 = a15 == 0;
  }
  v66 = v29;
  v68 = &a16;
  v67 = 0;
  v70 = &a17;
  if ( v34 )
    v33 = "NULL";
  v65 = v33;
  v72 = &a18;
  v69 = 4;
  v74 = &a19;
  v76 = &a20;
  v78 = &a21;
  v80 = &a22;
  v71 = 4;
  v73 = 4;
  v75 = 4;
  v77 = 4;
  v79 = 4;
  v81 = 8;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v33,
           (const EVENT_DESCRIPTOR *)CleanmgrPluginPurgeStop,
           v29,
           0x15u,
           &v37);
}

```

## disassembly

```asm
0x140016418  mov     [rsp-8+arg_0], rbx
0x14001641d  push    rbp
0x14001641e  lea     rbp, [rsp-0A0h]
0x140016426  sub     rsp, 1A0h
0x14001642d  mov     rax, cs:__security_cookie
0x140016434  xor     rax, rsp
0x140016437  mov     [rbp+0A0h+var_10], rax
0x14001643e  lea     rax, [rsp+1A0h+var_170]
0x140016443  mov     [rsp+1A0h+var_170], 2
0x14001644b  xor     r10d, r10d
0x14001644e  mov     [rsp+1A0h+var_150], rax
0x140016453  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016457  mov     [rsp+1A0h+var_148], 4
0x140016460  lea     r8d, [r10+0Ah]
0x140016464  test    r9, r9
0x140016467  jz      short loc_14001647F
0x140016469  mov     rcx, rax
0x14001646c  inc     rcx
0x14001646f  cmp     [r9+rcx*2], r10w
0x140016474  jnz     short loc_14001646C
0x140016476  lea     ecx, ds:2[rcx*2]
0x14001647d  jmp     short loc_140016482
0x14001647f  mov     ecx, r8d
0x140016482  mov     rdx, [rbp+0A0h+arg_30]
0x140016489  lea     rbx, aNull_0; "NULL"
0x140016490  mov     [rsp+1A0h+var_138], ecx
0x140016494  test    r9, r9
0x140016497  lea     rcx, [rbp+0A0h+arg_20]
0x14001649e  mov     [rsp+1A0h+var_134], r10d
0x1400164a3  cmovz   r9, rbx
0x1400164a7  mov     [rsp+1A0h+var_130], rcx
0x1400164ac  mov     [rsp+1A0h+var_140], r9
0x1400164b1  lea     rcx, [rbp+0A0h+arg_28]
0x1400164b8  mov     [rbp+0A0h+var_120], rcx
0x1400164bc  mov     [rsp+1A0h+var_128], 4
0x1400164c5  mov     [rbp+0A0h+var_118], 4
0x1400164cd  test    rdx, rdx
0x1400164d0  jz      short loc_1400164EA
0x1400164d2  mov     rcx, rax
0x1400164d5  inc     rcx
0x1400164d8  cmp     [rdx+rcx*2], r10w
0x1400164dd  jnz     short loc_1400164D5
0x1400164df  lea     r8d, ds:2[rcx*2]
0x1400164e7  test    rdx, rdx
0x1400164ea  lea     rcx, [rbp+0A0h+arg_38]
0x1400164f1  mov     [rbp+0A0h+var_108], r8d
0x1400164f5  mov     [rbp+0A0h+var_100], rcx
0x1400164f9  cmovz   rdx, rbx
0x1400164fd  lea     rcx, [rbp+0A0h+arg_40]
0x140016504  mov     [rbp+0A0h+var_110], rdx
0x140016508  mov     [rbp+0A0h+var_F0], rcx
0x14001650c  mov     r8d, 5
0x140016512  lea     rcx, [rbp+0A0h+arg_48]
0x140016519  mov     [rbp+0A0h+var_104], r10d
0x14001651d  mov     [rbp+0A0h+var_E0], rcx
0x140016521  lea     rcx, [rbp+0A0h+arg_50]
0x140016528  mov     [rbp+0A0h+var_D0], rcx
0x14001652c  lea     rcx, [rbp+0A0h+arg_58]
0x140016533  mov     [rbp+0A0h+var_C0], rcx
0x140016537  lea     rcx, [rbp+0A0h+arg_60]
0x14001653e  mov     [rbp+0A0h+var_B0], rcx
0x140016542  mov     rcx, [rbp+0A0h+arg_68]
0x140016549  mov     [rbp+0A0h+var_F8], 4
0x140016551  mov     [rbp+0A0h+var_E8], 8
0x140016559  mov     [rbp+0A0h+var_D8], 8
0x140016561  mov     [rbp+0A0h+var_C8], 8
0x140016569  mov     [rbp+0A0h+var_B8], 8
0x140016571  mov     [rbp+0A0h+var_A8], 8
0x140016579  test    rcx, rcx
0x14001657c  jz      short loc_14001658E
0x14001657e  mov     rdx, rax
0x140016581  inc     rdx
0x140016584  cmp     [rcx+rdx], r10b
0x140016588  jnz     short loc_140016581
0x14001658a  inc     edx
0x14001658c  jmp     short loc_140016591
0x14001658e  mov     edx, r8d
0x140016591  test    rcx, rcx
0x140016594  mov     [rbp+0A0h+var_98], edx
0x140016597  lea     rbx, aNull; "NULL"
0x14001659e  mov     [rbp+0A0h+var_94], r10d
0x1400165a2  cmovz   rcx, rbx
0x1400165a6  mov     [rbp+0A0h+var_A0], rcx
0x1400165aa  mov     rcx, [rbp+0A0h+arg_70]
0x1400165b1  test    rcx, rcx
0x1400165b4  jz      short loc_1400165C6
0x1400165b6  inc     rax
0x1400165b9  cmp     [rcx+rax], r10b
0x1400165bd  jnz     short loc_1400165B6
0x1400165bf  lea     r8d, [rax+1]
0x1400165c3  test    rcx, rcx
0x1400165c6  lea     rax, [rbp+0A0h+arg_78]
0x1400165cd  mov     [rbp+0A0h+var_88], r8d
0x1400165d1  mov     [rbp+0A0h+var_80], rax
0x1400165d5  lea     rdx, CleanmgrPluginPurgeStop
0x1400165dc  lea     rax, [rbp+0A0h+arg_80]
0x1400165e3  mov     [rbp+0A0h+var_84], r10d
0x1400165e7  mov     [rbp+0A0h+var_70], rax
0x1400165eb  cmovz   rcx, rbx
0x1400165ef  lea     rax, [rbp+0A0h+arg_88]
0x1400165f6  mov     [rbp+0A0h+var_90], rcx
0x1400165fa  mov     [rbp+0A0h+var_60], rax
0x1400165fe  mov     r9d, 15h
0x140016604  lea     rax, [rbp+0A0h+arg_90]
0x14001660b  mov     [rbp+0A0h+var_78], 4
0x140016613  mov     [rbp+0A0h+var_50], rax
0x140016617  lea     rax, [rbp+0A0h+arg_98]
0x14001661e  mov     [rbp+0A0h+var_40], rax
0x140016622  lea     rax, [rbp+0A0h+arg_A0]
0x140016629  mov     [rbp+0A0h+var_30], rax
0x14001662d  lea     rax, [rbp+0A0h+arg_A8]
0x140016634  mov     [rbp+0A0h+var_20], rax
0x14001663b  lea     rax, [rsp+1A0h+var_160]
0x140016640  mov     [rsp+1A0h+var_180], rax
0x140016645  mov     [rbp+0A0h+var_68], 4
0x14001664d  mov     [rbp+0A0h+var_58], 4
0x140016655  mov     [rbp+0A0h+var_48], 4
0x14001665d  mov     [rbp+0A0h+var_38], 4
0x140016665  mov     [rbp+0A0h+var_28], 4
0x14001666d  mov     [rbp+0A0h+var_18], 8
0x140016678  call    McGenEventWrite_EventWriteTransfer
0x14001667d  mov     rcx, [rbp+0A0h+var_10]
0x140016684  xor     rcx, rsp; StackCookie
0x140016687  call    __security_check_cookie
0x14001668c  mov     rbx, [rsp+1A0h+arg_0]
0x140016694  add     rsp, 1A0h
0x14001669b  pop     rbp
0x14001669c  retn
```
