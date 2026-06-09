# CLstBxWinHost::accDoDefaultAction(tagVARIANT)

- ea: `0x1800622a0`
- end: `0x18006257c`
- name: `?accDoDefaultAction@CLstBxWinHost@@UEAAJUtagVARIANT@@@Z`
- size: `732`
- prototype: `int(CLstBxWinHost *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180062130`
- `0x1800622a0`
- `0x18008cfc0`
- `0x1800907ac`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!MessageBeep` at `0x18006251a`
- `USER32!MessageBeep` at `0x18006251a`
- `USER32!WindowFromPoint` at `0x180062390`
- `USER32!WindowFromPoint` at `0x180062390`
- `USER32!SystemParametersInfoW` at `0x18006240e`
- `USER32!SystemParametersInfoW` at `0x180062436`
- `USER32!SystemParametersInfoW` at `0x180062532`
- `USER32!SystemParametersInfoW` at `0x18006240e`
- `USER32!SystemParametersInfoW` at `0x180062436`
- `USER32!SystemParametersInfoW` at `0x180062532`
- `USER32!GetCursorPos` at `0x1800623b7`
- `USER32!GetCursorPos` at `0x1800623b7`
- `USER32!GetSystemMetrics` at `0x1800623c1`
- `USER32!GetSystemMetrics` at `0x180062449`
- `USER32!GetSystemMetrics` at `0x1800623c1`
- `USER32!GetSystemMetrics` at `0x180062449`

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
    v24 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, __int64))qword_1800A44A0;
    v35[2 * v23] = 0;
    v38[2 * v23] = 1;
    v39[v23] = 0;
    *(&v36.x + 2 * v23) = -x;
    *(&v36.y + 2 * v23) = -y;
    v38[2 * v23 - 1] = v19;
    if ( !v24
      && (SetProcAddr(&qword_1800A44A0, 3, "SendInput"),
          (v24 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, __int64))qword_1800A44A0) == 0)
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
0x1800622a0  mov     [rsp-8+arg_10], rbx
0x1800622a5  push    rbp
0x1800622a6  push    rsi
0x1800622a7  push    rdi
0x1800622a8  push    r12
0x1800622aa  push    r13
0x1800622ac  push    r14
0x1800622ae  push    r15
0x1800622b0  lea     rbp, [rsp-0A0h]
0x1800622b8  sub     rsp, 1A0h
0x1800622bf  mov     rax, cs:__security_cookie
0x1800622c6  xor     rax, rsp
0x1800622c9  mov     [rbp+0D0h+var_40], rax
0x1800622d0  mov     rbx, rdx
0x1800622d3  mov     rdi, rcx
0x1800622d6  mov     edx, [rcx+0B8h]; struct tagVARIANT *
0x1800622dc  mov     rcx, rbx; this
0x1800622df  call    ?ValidateChild@MSAA@@YAHPEAUtagVARIANT@@H@Z; MSAA::ValidateChild(tagVARIANT *,int)
0x1800622e4  xor     r12d, r12d
0x1800622e7  test    eax, eax
0x1800622e9  jnz     short loc_1800622F5
0x1800622eb  mov     eax, 80070057h
0x1800622f0  jmp     loc_180062552
0x1800622f5  cmp     [rbx+8], r12d
0x1800622f9  jz      loc_18006254D
0x1800622ff  mov     rax, [rdi]
0x180062302  lea     rcx, [rsp+1D0h+var_180]
0x180062307  movups  xmm1, xmmword ptr [rbx]
0x18006230a  mov     [rsp+1D0h+var_1A8], rcx
0x18006230f  lea     r9, [rsp+1D0h+var_158]
0x180062314  xorps   xmm0, xmm0
0x180062317  lea     rcx, [rsp+1D0h+var_154]
0x18006231c  mov     rax, [rax+0B0h]
0x180062323  lea     r8, [rsp+1D0h+var_15C]
0x180062328  movups  xmmword ptr [rsp+70h], xmm0
0x18006232d  lea     rdx, [rsp+1D0h+var_160]
0x180062332  mov     [rsp+1D0h+var_1B0], rcx
0x180062337  movsd   xmm0, qword ptr [rbx+10h]
0x18006233c  mov     rcx, rdi
0x18006233f  movaps  [rsp+1D0h+var_180], xmm1
0x180062344  movsd   [rsp+1D0h+var_170], xmm0
0x18006234a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006234f  test    eax, eax
0x180062351  js      loc_180062552
0x180062357  mov     eax, [rsp+1D0h+var_158]
0x18006235b  mov     r8d, 2
0x180062361  mov     r14d, [rsp+1D0h+var_160]
0x180062366  cdq
0x180062367  mov     r15d, [rsp+1D0h+var_15C]
0x18006236c  mov     rbx, [rdi+8]
0x180062370  idiv    r8d
0x180062373  add     r14d, eax
0x180062376  mov     eax, [rsp+1D0h+var_154]
0x18006237a  cdq
0x18006237b  mov     [rsp+1D0h+Point.x], r14d
0x180062380  idiv    r8d
0x180062383  add     r15d, eax
0x180062386  mov     [rsp+1D0h+Point.y], r15d
0x18006238b  mov     rcx, qword ptr [rsp+1D0h+Point.x]; Point
0x180062390  call    cs:__imp_WindowFromPoint
0x180062396  cmp     rax, rbx
0x180062399  jnz     loc_18006254D
0x18006239f  mov     r13d, 1
0x1800623a5  mov     ecx, r13d; int
0x1800623a8  call    ?BlockInput@CW32System@@SAHH@Z; CW32System::BlockInput(int)
0x1800623ad  lea     rcx, [rsp+1D0h+var_190]; lpPoint
0x1800623b2  mov     qword ptr [rsp+1D0h+var_190.x], r12
0x1800623b7  call    cs:__imp_GetCursorPos
0x1800623bd  lea     ecx, [r13+16h]; nIndex
0x1800623c1  call    cs:__imp_GetSystemMetrics
0x1800623c7  mov     ecx, eax
0x1800623c9  lea     r8, [rbp+0D0h+pvParam]; pvParam
0x1800623cd  neg     ecx
0x1800623cf  sbb     edi, edi
0x1800623d1  and     edi, 0Ch
0x1800623d4  neg     eax
0x1800623d6  sbb     esi, esi
0x1800623d8  sub     r14d, [rsp+1D0h+var_190.x]
0x1800623dd  sub     r15d, [rsp+1D0h+var_190.y]
0x1800623e2  xor     eax, eax
0x1800623e4  mov     [rsp+1D0h+var_190.x], r14d
0x1800623e9  and     esi, 6
0x1800623ec  lea     r14d, [r13+2]
0x1800623f0  mov     [rsp+1D0h+var_190.y], r15d
0x1800623f5  mov     ecx, r14d; uiAction
0x1800623f8  mov     [rbp+0D0h+pvParam], rax
0x1800623fc  xor     r9d, r9d; fWinIni
0x1800623ff  mov     [rbp+0D0h+var_138], eax
0x180062402  xor     edx, edx; uiParam
0x180062404  mov     [rbp+0D0h+var_150], rax
0x180062408  add     esi, 2
0x18006240b  mov     [rbp+0D0h+var_148], eax
0x18006240e  call    cs:__imp_SystemParametersInfoW
0x180062414  test    eax, eax
0x180062416  jz      loc_18006253D
0x18006241c  cmp     [rbp+0D0h+var_138], r12d
0x180062420  jz      short loc_180062444
0x180062422  xor     edx, edx; uiParam
0x180062424  mov     [rbp+0D0h+var_150], r12
0x180062428  xor     r9d, r9d; fWinIni
0x18006242b  mov     [rbp+0D0h+var_148], r12d
0x18006242f  lea     r8, [rbp+0D0h+var_150]; pvParam
0x180062433  lea     ecx, [rdx+4]; uiAction
0x180062436  call    cs:__imp_SystemParametersInfoW
0x18006243c  test    eax, eax
0x18006243e  jz      loc_18006253D
0x180062444  mov     ecx, 2Bh ; '+'; nIndex
0x180062449  call    cs:__imp_GetSystemMetrics
0x18006244f  mov     r8d, [rsp+1D0h+var_190.x]
0x180062454  mov     ebx, r13d
0x180062457  mov     r9d, [rsp+1D0h+var_190.y]
0x18006245c  mov     r10d, eax
0x18006245f  mov     dword ptr [rbp+0D0h+var_128], r8d
0x180062463  mov     rdx, r13
0x180062466  mov     dword ptr [rbp+0D0h+var_128+4], r9d
0x18006246a  mov     [rbp+0D0h+var_120], eax
0x18006246d  mov     [rbp+0D0h+var_130], r12d
0x180062471  mov     [rbp+0D0h+var_11C], r13d
0x180062475  mov     [rbp+0D0h+var_110], r12
0x180062479  lea     rcx, [rdx+rdx*4]
0x18006247d  test    r13b, bl
0x180062480  lea     eax, [rdi+4]
0x180062483  cmovnz  eax, esi
0x180062486  add     ebx, r13d
0x180062489  mov     [rbp+rcx*8+0D0h+var_11C], eax
0x18006248d  add     rdx, r13
0x180062490  mov     [rbp+rcx*8+0D0h+var_130], r12d
0x180062495  mov     [rbp+rcx*8+0D0h+var_110], r12
0x18006249a  mov     [rbp+rcx*8+0D0h+var_128], r12
0x18006249f  mov     [rbp+rcx*8+0D0h+var_120], r10d
0x1800624a4  cmp     ebx, 4
0x1800624a7  jle     short loc_180062479
0x1800624a9  movsxd  rax, ebx
0x1800624ac  neg     r8d
0x1800624af  neg     r9d
0x1800624b2  lea     rcx, [rax+rax*4]
0x1800624b6  mov     rax, cs:qword_1800A44A0
0x1800624bd  mov     [rbp+rcx*8+0D0h+var_130], r12d
0x1800624c2  mov     [rbp+rcx*8+0D0h+var_11C], r13d
0x1800624c7  mov     [rbp+rcx*8+0D0h+var_110], r12
0x1800624cc  mov     dword ptr [rbp+rcx*8+0D0h+var_128], r8d
0x1800624d1  mov     dword ptr [rbp+rcx*8+0D0h+var_128+4], r9d
0x1800624d6  mov     [rbp+rcx*8+0D0h+var_120], r10d
0x1800624db  test    rax, rax
0x1800624de  jnz     short loc_180062502
0x1800624e0  lea     r8, aSendinput; "SendInput"
0x1800624e7  mov     edx, r14d
0x1800624ea  lea     rcx, qword_1800A44A0
0x1800624f1  call    SetProcAddr
0x1800624f6  mov     rax, cs:qword_1800A44A0
0x1800624fd  test    rax, rax
0x180062500  jz      short loc_180062518
0x180062502  lea     ecx, [rbx+1]
0x180062505  mov     r8d, 28h ; '('
0x18006250b  lea     rdx, [rbp+0D0h+var_130]
0x18006250f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062514  test    eax, eax
0x180062516  jnz     short loc_180062520
0x180062518  xor     ecx, ecx; uType
0x18006251a  call    cs:__imp_MessageBeep
0x180062520  cmp     [rbp+0D0h+var_138], r12d
0x180062524  jz      short loc_180062538
0x180062526  xor     edx, edx; uiParam
0x180062528  lea     r8, [rbp+0D0h+pvParam]; pvParam
0x18006252c  xor     r9d, r9d; fWinIni
0x18006252f  lea     ecx, [rdx+4]; uiAction
0x180062532  call    cs:__imp_SystemParametersInfoW
0x180062538  mov     ebx, r12d
0x18006253b  jmp     short loc_180062542
0x18006253d  mov     ebx, 80020003h
0x180062542  xor     ecx, ecx; int
0x180062544  call    ?BlockInput@CW32System@@SAHH@Z; CW32System::BlockInput(int)
0x180062549  mov     eax, ebx
0x18006254b  jmp     short loc_180062552
0x18006254d  mov     eax, 80020003h
0x180062552  mov     rcx, [rbp+0D0h+var_40]
0x180062559  xor     rcx, rsp; StackCookie
0x18006255c  call    __security_check_cookie
0x180062561  mov     rbx, [rsp+1D0h+arg_10]
0x180062569  add     rsp, 1A0h
0x180062570  pop     r15
0x180062572  pop     r14
0x180062574  pop     r13
0x180062576  pop     r12
0x180062578  pop     rdi
0x180062579  pop     rsi
0x18006257a  pop     rbp
0x18006257b  retn
```
