# MvVisitKeysFromBytes__lambda_06f2a676e6a644b54fec8940156dc900_

- ea: `0x180036710`
- end: `0x180036b13`
- name: `MvVisitKeysFromBytes__lambda_06f2a676e6a644b54fec8940156dc900___`
- size: `1027`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036b1c`

## callees

- `0x180012d80`
- `0x180014a6c`
- `0x180036710`
- `0x18003f010`

## string_xrefs

- `0x180036a71`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`
- `0x180036a86`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`
- `0x1800369f6`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036a0b`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036a23`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036a3e`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036a59`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036a98`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036aad`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036ac2`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036ad7`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036ae9`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`
- `0x180036afe`: `onecoreuap\admin\prov\multivariant\common\inc\mvProvisionDataHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall MvVisitKeysFromBytes__lambda_06f2a676e6a644b54fec8940156dc900_(__int64 a1, int a2, __int64 a3)
{
  char v3; // al
  unsigned __int64 v4; // r12
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned int v7; // r13d
  char *v8; // r14
  unsigned __int64 v9; // rcx
  char *i; // rax
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // ebx
  char *v18; // r15
  unsigned __int64 v19; // rcx
  char *j; // rax
  __int64 v21; // r9
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned int v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // ebp
  __int64 *v27; // rsi
  int v28; // eax
  int v29; // eax
  __int64 v30; // r8
  _DWORD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v35; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v37; // [rsp+70h] [rbp+8h] BYREF
  __int64 v38; // [rsp+80h] [rbp+18h]

  v38 = a3;
  if ( *(_DWORD *)a1 != a2 || (v3 = 0, *(_DWORD *)a1 < 0xCu) )
    v3 = 1;
  if ( v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
      (const char *)0x8000FFFFLL,
      v35);
  if ( *(_WORD *)(a1 + 4) != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
      (const char *)0x8000FFFFLL,
      v35);
  v4 = *(unsigned int *)(a1 + 8);
  v5 = a2 - 12;
  if ( !(_DWORD)v4 && a2 != 12 || (LOBYTE(v6) = 0, (v5 & 1) != 0) )
    LOBYTE(v6) = 1;
  if ( (_BYTE)v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
      (const char *)0x80070057LL,
      v35);
  if ( (_DWORD)v4 )
  {
    v7 = 0;
    v8 = (char *)(a1 + 12);
    do
    {
      if ( v5 < 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          (const char *)0x80070057LL,
          v35);
      if ( v8 )
      {
        v9 = (unsigned __int64)v5 >> 1;
        for ( i = v8; v9; --v9 )
        {
          if ( !*(_WORD *)i )
            break;
          i += 2;
        }
        v11 = v9 == 0 ? 0x80070057 : 0;
        if ( v9 )
          v12 = ((unsigned __int64)v5 >> 1) - v9;
        else
          v12 = 0;
        if ( v9 )
        {
          v13 = 2 * v12;
          goto LABEL_25;
        }
      }
      else
      {
        v11 = 2147942487LL;
      }
      v13 = 0;
LABEL_25:
      if ( (int)v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x47,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          (const char *)v11,
          v35);
      v14 = v13;
      if ( v13 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          v13 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          v35);
      v15 = v13 + 2;
      v16 = -1;
      if ( v14 + 2 >= v14 )
        v16 = v14 + 2;
      if ( v15 < v14 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          v15 < v14 ? (const char *)0x80070216LL : 0,
          v35);
      v17 = v5 - v16;
      if ( v17 < 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          (const char *)0x80070057LL,
          v35);
      v18 = &v8[v16];
      if ( !v18 )
      {
        v21 = 2147942487LL;
LABEL_42:
        v23 = 0;
        goto LABEL_43;
      }
      v19 = (unsigned __int64)v17 >> 1;
      for ( j = &v8[v16]; v19; --v19 )
      {
        if ( !*(_WORD *)j )
          break;
        j += 2;
      }
      v21 = v19 == 0 ? 0x80070057 : 0;
      if ( v19 )
        v22 = ((unsigned __int64)v17 >> 1) - v19;
      else
        v22 = 0;
      if ( !v19 )
        goto LABEL_42;
      v23 = 2 * v22;
LABEL_43:
      if ( (int)v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          (const char *)v21,
          v35);
      v24 = v23;
      if ( v23 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          v23 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          v35);
      v25 = v23 + 2;
      v26 = -1;
      if ( v24 + 2 >= v24 )
        v26 = v24 + 2;
      if ( v25 < v24 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvProvisionDataHelper.h",
          v25 < v24 ? (const char *)0x80070216LL : 0,
          v35);
      v27 = *(__int64 **)a3;
      if ( !**(_QWORD **)a3 )
      {
        co_array_t<IMVKey *>::allocate(*(_QWORD *)a3, v4);
        a3 = v38;
      }
      v37 = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(***(_QWORD ***)(a3 + 8) + 24LL))(
              **(_QWORD **)(a3 + 8),
              0,
              &GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0,
              &v37);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
          (const char *)(unsigned int)v28,
          v35);
      v29 = (*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v37 + 24LL))(v37, v8, v18);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
          (const char *)(unsigned int)v29,
          v35);
      v30 = v37;
      v37 = 0;
      v31 = *(_DWORD **)(v38 + 16);
      v32 = (unsigned int)*v31;
      *v31 = v32 + 1;
      v6 = *v27;
      *(_QWORD *)(*v27 + 8 * v32) = v30;
      v33 = v37;
      if ( v37 )
      {
        v37 = 0;
        LOBYTE(v6) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v8 = &v18[v26];
      v5 = v17 - v26;
      ++v7;
      a3 = v38;
    }
    while ( v7 < (unsigned int)v4 );
  }
  return v6;
}

```

## disassembly

```asm
0x180036710  mov     [rsp+arg_8], rbx
0x180036715  mov     [rsp+arg_10], r8
0x18003671a  push    rbp
0x18003671b  push    rsi
0x18003671c  push    rdi
0x18003671d  push    r12
0x18003671f  push    r13
0x180036721  push    r14
0x180036723  push    r15
0x180036725  sub     rsp, 30h
0x180036729  mov     ebp, 1
0x18003672e  xor     r11d, r11d
0x180036731  cmp     [rcx], edx
0x180036733  jnz     short loc_18003673D
0x180036735  cmp     dword ptr [rcx], 0Ch
0x180036738  mov     al, r11b
0x18003673b  jnb     short loc_180036740
0x18003673d  mov     al, bpl
0x180036740  mov     r10, [rsp+68h]
0x180036745  test    al, al
0x180036747  jnz     loc_180036A1D
0x18003674d  mov     rax, [rsp+68h]
0x180036752  cmp     bp, [rcx+4]
0x180036756  jnz     loc_180036A38
0x18003675c  mov     r12d, [rcx+8]
0x180036760  lea     ebx, [rdx-0Ch]
0x180036763  test    r12d, r12d
0x180036766  jnz     short loc_18003676C
0x180036768  test    ebx, ebx
0x18003676a  jnz     short loc_180036777
0x18003676c  mov     eax, ebx
0x18003676e  and     eax, ebp
0x180036770  test    al, al
0x180036772  mov     al, r11b
0x180036775  jz      short loc_18003677A
0x180036777  mov     al, bpl
0x18003677a  mov     r10, [rsp+68h]
0x18003677f  test    al, al
0x180036781  jnz     loc_180036A53
0x180036787  test    r12d, r12d
0x18003678a  jz      loc_1800369E1
0x180036790  mov     r13d, r11d
0x180036793  lea     r14, [rcx+0Ch]
0x180036797  mov     edi, 80070057h
0x18003679c  mov     esi, 0FFFFFFFFh
0x1800367a1  mov     rcx, [rsp+68h]; this
0x1800367a6  cmp     ebx, 2
0x1800367a9  jb      loc_180036A08
0x1800367af  test    r14, r14
0x1800367b2  jz      short loc_1800367F7
0x1800367b4  mov     ecx, ebx
0x1800367b6  shr     rcx, 1
0x1800367b9  mov     rax, r14
0x1800367bc  mov     rdx, rcx
0x1800367bf  jz      short loc_1800367D0
0x1800367c1  cmp     [rax], r11w
0x1800367c5  jz      short loc_1800367D0
0x1800367c7  add     rax, 2
0x1800367cb  sub     rcx, rbp
0x1800367ce  jnz     short loc_1800367C1
0x1800367d0  mov     rax, rcx
0x1800367d3  neg     rax
0x1800367d6  sbb     r9d, r9d
0x1800367d9  not     r9d
0x1800367dc  and     r9d, edi
0x1800367df  test    rcx, rcx
0x1800367e2  jz      short loc_1800367E9
0x1800367e4  sub     rdx, rcx
0x1800367e7  jmp     short loc_1800367EC
0x1800367e9  mov     rdx, r11
0x1800367ec  test    rcx, rcx
0x1800367ef  jz      short loc_1800367FA
0x1800367f1  lea     rax, [rdx+rdx]
0x1800367f5  jmp     short loc_1800367FD
0x1800367f7  mov     r9d, edi; char *
0x1800367fa  mov     rax, r11
0x1800367fd  mov     rcx, [rsp+68h]; this
0x180036802  test    r9d, r9d
0x180036805  js      loc_1800369F6
0x18003680b  cmp     rax, rsi
0x18003680e  mov     ecx, eax
0x180036810  jbe     short loc_180036814
0x180036812  mov     ecx, esi
0x180036814  cmp     rsi, rax
0x180036817  sbb     r9d, r9d
0x18003681a  and     r9d, 80070216h; char *
0x180036821  mov     r10, [rsp+68h]
0x180036826  cmp     rax, rsi
0x180036829  ja      loc_180036AFE
0x18003682f  lea     eax, [rcx+2]
0x180036832  mov     edx, esi
0x180036834  cmp     eax, ecx
0x180036836  cmovnb  edx, eax
0x180036839  sbb     r9d, r9d
0x18003683c  and     r9d, 80070216h; char *
0x180036843  mov     r10, [rsp+68h]
0x180036848  cmp     eax, ecx
0x18003684a  jb      loc_180036AE9
0x180036850  sub     ebx, edx
0x180036852  mov     rcx, [rsp+68h]; this
0x180036857  cmp     ebx, 2
0x18003685a  jb      loc_180036AD4
0x180036860  mov     r15d, edx
0x180036863  add     r15, r14
0x180036866  jz      short loc_1800368AB
0x180036868  mov     ecx, ebx
0x18003686a  shr     rcx, 1
0x18003686d  mov     rax, r15
0x180036870  mov     rdx, rcx
0x180036873  jz      short loc_180036884
0x180036875  cmp     [rax], r11w
0x180036879  jz      short loc_180036884
0x18003687b  add     rax, 2
0x18003687f  sub     rcx, rbp
0x180036882  jnz     short loc_180036875
0x180036884  mov     rax, rcx
0x180036887  neg     rax
0x18003688a  sbb     r9d, r9d
0x18003688d  not     r9d
0x180036890  and     r9d, edi
0x180036893  test    rcx, rcx
0x180036896  jz      short loc_18003689D
0x180036898  sub     rdx, rcx
0x18003689b  jmp     short loc_1800368A0
0x18003689d  mov     rdx, r11
0x1800368a0  test    rcx, rcx
0x1800368a3  jz      short loc_1800368AE
0x1800368a5  lea     rax, [rdx+rdx]
0x1800368a9  jmp     short loc_1800368B1
0x1800368ab  mov     r9d, edi; char *
0x1800368ae  mov     rax, r11
0x1800368b1  mov     rcx, [rsp+68h]; this
0x1800368b6  test    r9d, r9d
0x1800368b9  js      loc_180036AC2
0x1800368bf  cmp     rax, rsi
0x1800368c2  mov     ecx, eax
0x1800368c4  jbe     short loc_1800368C8
0x1800368c6  mov     ecx, esi
0x1800368c8  cmp     rsi, rax
0x1800368cb  sbb     r9d, r9d
0x1800368ce  mov     edx, 80070216h
0x1800368d3  and     r9d, edx; char *
0x1800368d6  mov     r10, [rsp+68h]
0x1800368db  cmp     rax, rsi
0x1800368de  ja      loc_180036AAD
0x1800368e4  lea     eax, [rcx+2]
0x1800368e7  mov     ebp, esi
0x1800368e9  cmp     eax, ecx
0x1800368eb  cmovnb  ebp, eax
0x1800368ee  sbb     r9d, r9d
0x1800368f1  and     r9d, edx; char *
0x1800368f4  mov     r10, [rsp+68h]
0x1800368f9  cmp     eax, ecx
0x1800368fb  jb      loc_180036A98
0x180036901  mov     rsi, [r8]
0x180036904  cmp     [rsi], r11
0x180036907  jnz     short loc_18003691F
0x180036909  mov     rdx, r12
0x18003690c  mov     rcx, rsi
0x18003690f  call    ?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z; co_array_t<IMVKey *>::allocate(unsigned __int64)
0x180036914  mov     r8, [rsp+68h+arg_10]
0x18003691c  xor     r11d, r11d
0x18003691f  mov     [rsp+68h+arg_0], r11
0x180036924  mov     rax, [r8+8]
0x180036928  mov     rcx, [rax]
0x18003692b  mov     rax, [rcx]
0x18003692e  lea     r9, [rsp+68h+arg_0]
0x180036933  lea     r8, _GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0
0x18003693a  xor     edx, edx
0x18003693c  mov     rax, [rax+18h]
0x180036940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036945  mov     rcx, [rsp+68h]; this
0x18003694a  test    eax, eax
0x18003694c  js      loc_180036A83
0x180036952  mov     rcx, [rsp+68h+arg_0]
0x180036957  mov     rax, [rcx]
0x18003695a  mov     r8, r15
0x18003695d  mov     rdx, r14
0x180036960  mov     rax, [rax+18h]
0x180036964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036969  mov     rcx, [rsp+68h]; this
0x18003696e  xor     r11d, r11d
0x180036971  test    eax, eax
0x180036973  js      loc_180036A6E
0x180036979  mov     r8, [rsp+68h+arg_0]
0x18003697e  mov     [rsp+68h+arg_0], r11
0x180036983  mov     rcx, [rsp+68h+arg_10]
0x18003698b  mov     rcx, [rcx+10h]
0x18003698f  mov     edx, [rcx]
0x180036991  lea     eax, [rdx+1]
0x180036994  mov     [rcx], eax
0x180036996  mov     rax, [rsi]
0x180036999  mov     [rax+rdx*8], r8
0x18003699d  mov     rcx, [rsp+68h+arg_0]
0x1800369a2  test    rcx, rcx
0x1800369a5  jz      short loc_1800369BB
0x1800369a7  mov     [rsp+68h+arg_0], r11
0x1800369ac  mov     rax, [rcx]
0x1800369af  mov     rax, [rax+10h]
0x1800369b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369b8  xor     r11d, r11d
0x1800369bb  mov     r14d, ebp
0x1800369be  add     r14, r15
0x1800369c1  sub     ebx, ebp
0x1800369c3  mov     ebp, 1
0x1800369c8  add     r13d, ebp
0x1800369cb  cmp     r13d, r12d
0x1800369ce  mov     r8, [rsp+68h+arg_10]
0x1800369d6  mov     esi, 0FFFFFFFFh
0x1800369db  jb      loc_1800367A1
0x1800369e1  mov     rbx, [rsp+68h+arg_8]
0x1800369e6  add     rsp, 30h
0x1800369ea  pop     r15
0x1800369ec  pop     r14
0x1800369ee  pop     r13
0x1800369f0  pop     r12
0x1800369f2  pop     rdi
0x1800369f3  pop     rsi
0x1800369f4  pop     rbp
0x1800369f5  retn
0x1800369f6  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800369fd  mov     edx, 47h ; 'G'; void *
0x180036a02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a08  mov     r9d, edi; char *
0x180036a0b  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a12  mov     edx, 44h ; 'D'; void *
0x180036a17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a1d  mov     r9d, 8000FFFFh; char *
0x180036a23  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a2a  mov     edx, 32h ; '2'; void *
0x180036a2f  mov     rcx, r10; this
0x180036a32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a38  mov     r9d, 8000FFFFh; char *
0x180036a3e  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a45  mov     edx, 38h ; '8'; void *
0x180036a4a  mov     rcx, rax; this
0x180036a4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a53  mov     r9d, 80070057h; char *
0x180036a59  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a60  mov     edx, 40h ; '@'; void *
0x180036a65  mov     rcx, r10; this
0x180036a68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a6e  mov     r9d, eax; char *
0x180036a71  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a78  mov     edx, 10Fh; void *
0x180036a7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a83  mov     r9d, eax; char *
0x180036a86  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a8d  mov     edx, 10Eh; void *
0x180036a92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036a98  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036a9f  mov     edx, 54h ; 'T'; void *
0x180036aa4  mov     rcx, r10; this
0x180036aa7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036aad  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036ab4  mov     edx, 53h ; 'S'; void *
0x180036ab9  mov     rcx, r10; this
0x180036abc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036ac2  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036ac9  mov     edx, 52h ; 'R'; void *
0x180036ace  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036ad4  mov     r9d, edi; char *
0x180036ad7  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036ade  mov     edx, 50h ; 'P'; void *
0x180036ae3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036ae9  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036af0  mov     edx, 4Ah ; 'J'; void *
0x180036af5  mov     rcx, r10; this
0x180036af8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036afe  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036b05  mov     edx, 49h ; 'I'; void *
0x180036b0a  mov     rcx, r10; this
0x180036b0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
