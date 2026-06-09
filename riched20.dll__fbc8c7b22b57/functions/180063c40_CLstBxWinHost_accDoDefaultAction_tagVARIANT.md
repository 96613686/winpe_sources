# CLstBxWinHost::accDoDefaultAction(tagVARIANT)

- ea: `0x180063c40`
- end: `0x180063f4d`
- name: `?accDoDefaultAction@CLstBxWinHost@@UEAAJUtagVARIANT@@@Z`
- size: `781`
- prototype: `int(CLstBxWinHost *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180063ac4`
- `0x180063c40`
- `0x18008f76c`
- `0x1800931b0`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!MessageBeep` at `0x180063ede`
- `USER32!MessageBeep` at `0x180063ede`
- `USER32!WindowFromPoint` at `0x180063d30`
- `USER32!WindowFromPoint` at `0x180063d30`
- `USER32!SystemParametersInfoW` at `0x180063dc0`
- `USER32!SystemParametersInfoW` at `0x180063dee`
- `USER32!SystemParametersInfoW` at `0x180063efc`
- `USER32!SystemParametersInfoW` at `0x180063dc0`
- `USER32!SystemParametersInfoW` at `0x180063dee`
- `USER32!SystemParametersInfoW` at `0x180063efc`
- `USER32!GetCursorPos` at `0x180063d5d`
- `USER32!GetCursorPos` at `0x180063d5d`
- `USER32!GetSystemMetrics` at `0x180063d6d`
- `USER32!GetSystemMetrics` at `0x180063e07`
- `USER32!GetSystemMetrics` at `0x180063d6d`
- `USER32!GetSystemMetrics` at `0x180063e07`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::accDoDefaultAction(HWND *this, struct tagVARIANT *a2, int a3)
{
  __int64 result; // rax
  __int128 v6; // xmm1
  __int64 (__fastcall *v7)(HWND *, __int128 *, char *, char *, char *, __int128 *); // rax
  IRecordInfo *pRecInfo; // xmm0_8
  HWND v9; // rbx
  LONG v10; // r14d
  LONG v11; // r15d
  int SystemMetrics; // eax
  int v13; // edi
  int v14; // esi
  int v15; // eax
  LONG x; // r8d
  int v17; // ebx
  LONG y; // r9d
  int v19; // r10d
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  unsigned int (__fastcall *v24)(_QWORD, _DWORD *, __int64); // rax
  unsigned int v25; // ebx
  struct tagPOINT v26; // [rsp+40h] [rbp-C0h] BYREF
  POINT Point; // [rsp+48h] [rbp-B8h]
  __int128 v28; // [rsp+50h] [rbp-B0h] BYREF
  IRecordInfo *v29; // [rsp+60h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+88h] [rbp-78h]
  __int64 pvParam; // [rsp+90h] [rbp-70h] BYREF
  int v34; // [rsp+98h] [rbp-68h]
  _DWORD v35[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagPOINT v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+B0h] [rbp-50h]
  _DWORD v38[3]; // [rsp+B4h] [rbp-4Ch]
  _QWORD v39[26]; // [rsp+C0h] [rbp-40h]

  if ( !(unsigned int)MSAA::ValidateChild((MSAA *)a2, (struct tagVARIANT *)*((unsigned int *)this + 46), a3) )
    return 2147942487LL;
  if ( !a2->lVal )
    return 2147614723LL;
  v6 = *(_OWORD *)&a2->vt;
  v7 = (__int64 (__fastcall *)(HWND *, __int128 *, char *, char *, char *, __int128 *))*((_QWORD *)*this + 22);
  v30 = 0;
  pRecInfo = a2->pRecInfo;
  v28 = v6;
  v29 = pRecInfo;
  result = v7(this, &v30, (char *)&v30 + 4, (char *)&v30 + 8, (char *)&v30 + 12, &v28);
  if ( (int)result < 0 )
    return result;
  v9 = this[1];
  v10 = SDWORD2(v30) / 2 + v30;
  Point.x = v10;
  v11 = SHIDWORD(v30) / 2 + DWORD1(v30);
  Point.y = v11;
  if ( WindowFromPoint(Point) != v9 )
    return 2147614723LL;
  CW32System::BlockInput(1);
  v26 = 0;
  GetCursorPos(&v26);
  SystemMetrics = GetSystemMetrics(23);
  v13 = SystemMetrics != 0 ? 0xC : 0;
  v26.x = v10 - v26.x;
  v26.y = v11 - v26.y;
  pvParam = 0;
  v34 = 0;
  v31 = 0;
  v14 = SystemMetrics != 0 ? 8 : 2;
  v32 = 0;
  if ( SystemParametersInfoW(3u, 0, &pvParam, 0) && (!v34 || (v31 = 0, v32 = 0, SystemParametersInfoW(4u, 0, &v31, 0))) )
  {
    v15 = GetSystemMetrics(43);
    x = v26.x;
    v17 = 1;
    y = v26.y;
    v19 = v15;
    v36 = v26;
    v20 = 1;
    v37 = v15;
    v35[0] = 0;
    v38[0] = 1;
    v39[0] = 0;
    do
    {
      v21 = 5 * v20;
      v22 = v13 + 4;
      if ( (v17 & 1) != 0 )
        v22 = v14;
      ++v17;
      v38[10 * v20++] = v22;
      v35[2 * v21] = 0;
      v39[v21] = 0;
      *((_QWORD *)&v36 + v21) = 0;
      v38[2 * v21 - 1] = v19;
    }
    while ( v17 <= 4 );
    v23 = 5LL * v17;
    v24 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, __int64))qword_1800A7580;
    v35[2 * v23] = 0;
    v38[2 * v23] = 1;
    v39[v23] = 0;
    *(&v36.x + 2 * v23) = -x;
    *(&v36.y + 2 * v23) = -y;
    v38[2 * v23 - 1] = v19;
    if ( !v24
      && (SetProcAddr(&qword_1800A7580, 3, "SendInput"),
          (v24 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, __int64))qword_1800A7580) == 0)
      || !v24((unsigned int)(v17 + 1), v35, 40) )
    {
      MessageBeep(0);
    }
    if ( v34 )
      SystemParametersInfoW(4u, 0, &pvParam, 0);
    v25 = 0;
  }
  else
  {
    v25 = -2147352573;
  }
  CW32System::BlockInput(0);
  return v25;
}

```

## disassembly

```asm
0x180063c40  mov     [rsp-8+arg_10], rbx
0x180063c45  push    rbp
0x180063c46  push    rsi
0x180063c47  push    rdi
0x180063c48  push    r12
0x180063c4a  push    r13
0x180063c4c  push    r14
0x180063c4e  push    r15
0x180063c50  lea     rbp, [rsp-0A0h]
0x180063c58  sub     rsp, 1A0h
0x180063c5f  mov     rax, cs:__security_cookie
0x180063c66  xor     rax, rsp
0x180063c69  mov     [rbp+0D0h+var_40], rax
0x180063c70  mov     rbx, rdx
0x180063c73  mov     rdi, rcx
0x180063c76  mov     edx, [rcx+0B8h]; struct tagVARIANT *
0x180063c7c  mov     rcx, rbx; this
0x180063c7f  call    ?ValidateChild@MSAA@@YAHPEAUtagVARIANT@@H@Z; MSAA::ValidateChild(tagVARIANT *,int)
0x180063c84  xor     r12d, r12d
0x180063c87  test    eax, eax
0x180063c89  jnz     short loc_180063C95
0x180063c8b  mov     eax, 80070057h
0x180063c90  jmp     loc_180063F22
0x180063c95  cmp     [rbx+8], r12d
0x180063c99  jz      loc_180063F1D
0x180063c9f  mov     rax, [rdi]
0x180063ca2  lea     rcx, [rsp+1D0h+var_180]
0x180063ca7  movups  xmm1, xmmword ptr [rbx]
0x180063caa  mov     [rsp+1D0h+var_1A8], rcx
0x180063caf  lea     r9, [rsp+1D0h+var_158]
0x180063cb4  xorps   xmm0, xmm0
0x180063cb7  lea     rcx, [rsp+1D0h+var_154]
0x180063cbc  mov     rax, [rax+0B0h]
0x180063cc3  lea     r8, [rsp+1D0h+var_15C]
0x180063cc8  movups  xmmword ptr [rsp+70h], xmm0
0x180063ccd  lea     rdx, [rsp+1D0h+var_160]
0x180063cd2  mov     [rsp+1D0h+var_1B0], rcx
0x180063cd7  movsd   xmm0, qword ptr [rbx+10h]
0x180063cdc  mov     rcx, rdi
0x180063cdf  movaps  [rsp+1D0h+var_180], xmm1
0x180063ce4  movsd   [rsp+1D0h+var_170], xmm0
0x180063cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cef  test    eax, eax
0x180063cf1  js      loc_180063F22
0x180063cf7  mov     eax, [rsp+1D0h+var_158]
0x180063cfb  mov     r8d, 2
0x180063d01  mov     r14d, [rsp+1D0h+var_160]
0x180063d06  cdq
0x180063d07  mov     r15d, [rsp+1D0h+var_15C]
0x180063d0c  mov     rbx, [rdi+8]
0x180063d10  idiv    r8d
0x180063d13  add     r14d, eax
0x180063d16  mov     eax, [rsp+1D0h+var_154]
0x180063d1a  cdq
0x180063d1b  mov     [rsp+1D0h+Point.x], r14d
0x180063d20  idiv    r8d
0x180063d23  add     r15d, eax
0x180063d26  mov     [rsp+1D0h+Point.y], r15d
0x180063d2b  mov     rcx, qword ptr [rsp+1D0h+Point.x]; Point
0x180063d30  call    cs:__imp_WindowFromPoint
0x180063d37  nop     dword ptr [rax+rax+00h]
0x180063d3c  cmp     rax, rbx
0x180063d3f  jnz     loc_180063F1D
0x180063d45  mov     r13d, 1
0x180063d4b  mov     ecx, r13d; int
0x180063d4e  call    ?BlockInput@CW32System@@SAHH@Z; CW32System::BlockInput(int)
0x180063d53  lea     rcx, [rsp+1D0h+var_190]; lpPoint
0x180063d58  mov     qword ptr [rsp+1D0h+var_190.x], r12
0x180063d5d  call    cs:__imp_GetCursorPos
0x180063d64  nop     dword ptr [rax+rax+00h]
0x180063d69  lea     ecx, [r13+16h]; nIndex
0x180063d6d  call    cs:__imp_GetSystemMetrics
0x180063d74  nop     dword ptr [rax+rax+00h]
0x180063d79  mov     ecx, eax
0x180063d7b  lea     r8, [rbp+0D0h+pvParam]; pvParam
0x180063d7f  neg     ecx
0x180063d81  sbb     edi, edi
0x180063d83  and     edi, 0Ch
0x180063d86  neg     eax
0x180063d88  sbb     esi, esi
0x180063d8a  sub     r14d, [rsp+1D0h+var_190.x]
0x180063d8f  sub     r15d, [rsp+1D0h+var_190.y]
0x180063d94  xor     eax, eax
0x180063d96  mov     [rsp+1D0h+var_190.x], r14d
0x180063d9b  and     esi, 6
0x180063d9e  lea     r14d, [r13+2]
0x180063da2  mov     [rsp+1D0h+var_190.y], r15d
0x180063da7  mov     ecx, r14d; uiAction
0x180063daa  mov     [rbp+0D0h+pvParam], rax
0x180063dae  xor     r9d, r9d; fWinIni
0x180063db1  mov     [rbp+0D0h+var_138], eax
0x180063db4  xor     edx, edx; uiParam
0x180063db6  mov     [rbp+0D0h+var_150], rax
0x180063dba  add     esi, 2
0x180063dbd  mov     [rbp+0D0h+var_148], eax
0x180063dc0  call    cs:__imp_SystemParametersInfoW
0x180063dc7  nop     dword ptr [rax+rax+00h]
0x180063dcc  test    eax, eax
0x180063dce  jz      loc_180063F0D
0x180063dd4  cmp     [rbp+0D0h+var_138], r12d
0x180063dd8  jz      short loc_180063E02
0x180063dda  xor     edx, edx; uiParam
0x180063ddc  mov     [rbp+0D0h+var_150], r12
0x180063de0  xor     r9d, r9d; fWinIni
0x180063de3  mov     [rbp+0D0h+var_148], r12d
0x180063de7  lea     r8, [rbp+0D0h+var_150]; pvParam
0x180063deb  lea     ecx, [rdx+4]; uiAction
0x180063dee  call    cs:__imp_SystemParametersInfoW
0x180063df5  nop     dword ptr [rax+rax+00h]
0x180063dfa  test    eax, eax
0x180063dfc  jz      loc_180063F0D
0x180063e02  mov     ecx, 2Bh ; '+'; nIndex
0x180063e07  call    cs:__imp_GetSystemMetrics
0x180063e0e  nop     dword ptr [rax+rax+00h]
0x180063e13  mov     r8d, [rsp+1D0h+var_190.x]
0x180063e18  mov     ebx, r13d
0x180063e1b  mov     r9d, [rsp+1D0h+var_190.y]
0x180063e20  mov     r10d, eax
0x180063e23  mov     dword ptr [rbp+0D0h+var_128], r8d
0x180063e27  mov     rdx, r13
0x180063e2a  mov     dword ptr [rbp+0D0h+var_128+4], r9d
0x180063e2e  mov     [rbp+0D0h+var_120], eax
0x180063e31  mov     [rbp+0D0h+var_130], r12d
0x180063e35  mov     [rbp+0D0h+var_11C], r13d
0x180063e39  mov     [rbp+0D0h+var_110], r12
0x180063e3d  lea     rcx, [rdx+rdx*4]
0x180063e41  test    r13b, bl
0x180063e44  lea     eax, [rdi+4]
0x180063e47  cmovnz  eax, esi
0x180063e4a  add     ebx, r13d
0x180063e4d  mov     [rbp+rcx*8+0D0h+var_11C], eax
0x180063e51  add     rdx, r13
0x180063e54  mov     [rbp+rcx*8+0D0h+var_130], r12d
0x180063e59  mov     [rbp+rcx*8+0D0h+var_110], r12
0x180063e5e  mov     [rbp+rcx*8+0D0h+var_128], r12
0x180063e63  mov     [rbp+rcx*8+0D0h+var_120], r10d
0x180063e68  cmp     ebx, 4
0x180063e6b  jle     short loc_180063E3D
0x180063e6d  movsxd  rax, ebx
0x180063e70  neg     r8d
0x180063e73  neg     r9d
0x180063e76  lea     rcx, [rax+rax*4]
0x180063e7a  mov     rax, cs:qword_1800A7580
0x180063e81  mov     [rbp+rcx*8+0D0h+var_130], r12d
0x180063e86  mov     [rbp+rcx*8+0D0h+var_11C], r13d
0x180063e8b  mov     [rbp+rcx*8+0D0h+var_110], r12
0x180063e90  mov     dword ptr [rbp+rcx*8+0D0h+var_128], r8d
0x180063e95  mov     dword ptr [rbp+rcx*8+0D0h+var_128+4], r9d
0x180063e9a  mov     [rbp+rcx*8+0D0h+var_120], r10d
0x180063e9f  test    rax, rax
0x180063ea2  jnz     short loc_180063EC6
0x180063ea4  lea     r8, aSendinput; "SendInput"
0x180063eab  mov     edx, r14d
0x180063eae  lea     rcx, qword_1800A7580
0x180063eb5  call    SetProcAddr
0x180063eba  mov     rax, cs:qword_1800A7580
0x180063ec1  test    rax, rax
0x180063ec4  jz      short loc_180063EDC
0x180063ec6  lea     ecx, [rbx+1]
0x180063ec9  mov     r8d, 28h ; '('
0x180063ecf  lea     rdx, [rbp+0D0h+var_130]
0x180063ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063ed8  test    eax, eax
0x180063eda  jnz     short loc_180063EEA
0x180063edc  xor     ecx, ecx; uType
0x180063ede  call    cs:__imp_MessageBeep
0x180063ee5  nop     dword ptr [rax+rax+00h]
0x180063eea  cmp     [rbp+0D0h+var_138], r12d
0x180063eee  jz      short loc_180063F08
0x180063ef0  xor     edx, edx; uiParam
0x180063ef2  lea     r8, [rbp+0D0h+pvParam]; pvParam
0x180063ef6  xor     r9d, r9d; fWinIni
0x180063ef9  lea     ecx, [rdx+4]; uiAction
0x180063efc  call    cs:__imp_SystemParametersInfoW
0x180063f03  nop     dword ptr [rax+rax+00h]
0x180063f08  mov     ebx, r12d
0x180063f0b  jmp     short loc_180063F12
0x180063f0d  mov     ebx, 80020003h
0x180063f12  xor     ecx, ecx; int
0x180063f14  call    ?BlockInput@CW32System@@SAHH@Z; CW32System::BlockInput(int)
0x180063f19  mov     eax, ebx
0x180063f1b  jmp     short loc_180063F22
0x180063f1d  mov     eax, 80020003h
0x180063f22  mov     rcx, [rbp+0D0h+var_40]
0x180063f29  xor     rcx, rsp; StackCookie
0x180063f2c  call    __security_check_cookie
0x180063f31  mov     rbx, [rsp+1D0h+arg_10]
0x180063f39  add     rsp, 1A0h
0x180063f40  pop     r15
0x180063f42  pop     r14
0x180063f44  pop     r13
0x180063f46  pop     r12
0x180063f48  pop     rdi
0x180063f49  pop     rsi
0x180063f4a  pop     rbp
0x180063f4b  retn
```
