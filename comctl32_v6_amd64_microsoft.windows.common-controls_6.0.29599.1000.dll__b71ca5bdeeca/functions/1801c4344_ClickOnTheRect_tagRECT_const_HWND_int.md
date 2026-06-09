# ClickOnTheRect(tagRECT const *,HWND__ *,int)

- ea: `0x1801c4344`
- end: `0x1801c45da`
- name: `?ClickOnTheRect@@YAHPEBUtagRECT@@PEAUHWND__@@H@Z`
- size: `662`
- prototype: `__int64 __fastcall(const struct tagRECT *, HWND, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18013f9d0`
- `0x18014eb80`
- `0x180160ae0`
- `0x180160bb0`

## callees

- `0x180114520`
- `0x18011550f`
- `0x1801c4344`
- `0x1801c46bc`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1801c4418`
- `USER32!SystemParametersInfoW` at `0x1801c4448`
- `USER32!SystemParametersInfoW` at `0x1801c45a9`
- `USER32!SystemParametersInfoW` at `0x1801c4418`
- `USER32!SystemParametersInfoW` at `0x1801c4448`
- `USER32!SystemParametersInfoW` at `0x1801c45a9`
- `USER32!GetKeyState` at `0x1801c4468`
- `USER32!GetKeyState` at `0x1801c447c`
- `USER32!GetKeyState` at `0x1801c448e`
- `USER32!GetKeyState` at `0x1801c4468`
- `USER32!GetKeyState` at `0x1801c447c`
- `USER32!GetKeyState` at `0x1801c448e`
- `USER32!GetCursorPos` at `0x1801c43ea`
- `USER32!GetCursorPos` at `0x1801c43ea`
- `USER32!GetSystemMetrics` at `0x1801c43be`
- `USER32!GetSystemMetrics` at `0x1801c445b`
- `USER32!GetSystemMetrics` at `0x1801c43be`
- `USER32!GetSystemMetrics` at `0x1801c445b`
- `USER32!WindowFromPoint` at `0x1801c43a0`
- `USER32!WindowFromPoint` at `0x1801c43a0`
- `USER32!SendInput` at `0x1801c455f`
- `USER32!SendInput` at `0x1801c455f`
- `USER32!BlockInput` at `0x1801c43b5`
- `USER32!BlockInput` at `0x1801c45b1`
- `USER32!BlockInput` at `0x1801c43b5`
- `USER32!BlockInput` at `0x1801c45b1`

## pseudocode

```c
__int64 __fastcall ClickOnTheRect(const struct tagRECT *a1, HWND a2)
{
  unsigned int v2; // r12d
  int v3; // edi
  int v4; // eax
  int v5; // esi
  int SystemMetrics; // eax
  int v7; // r14d
  int v8; // r15d
  unsigned int v9; // esi
  __int16 v10; // r13
  __int16 v11; // di
  int v12; // edx
  __int16 v13; // bx
  unsigned __int16 v14; // r9
  DWORD TickCount_0; // eax
  int v16; // edx
  unsigned __int16 v17; // r9
  _BYTE Point[12]; // [rsp+20h] [rbp-E0h] BYREF
  int pvParam_4; // [rsp+2Ch] [rbp-D4h]
  int v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h]
  tagINPUT pInputs; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+78h] [rbp-88h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  unsigned int v27; // [rsp+88h] [rbp-78h]
  int v28; // [rsp+8Ch] [rbp-74h]
  DWORD v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  unsigned int v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B4h] [rbp-4Ch]
  DWORD v35; // [rsp+B8h] [rbp-48h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D4h] [rbp-2Ch]
  unsigned int v40; // [rsp+D8h] [rbp-28h]
  int v41; // [rsp+DCh] [rbp-24h]
  DWORD v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]

  v2 = 0;
  v3 = a1->left + a1->right / 2;
  v4 = a1->bottom / 2;
  *(_DWORD *)Point = v3;
  v5 = a1->top + v4;
  *(_DWORD *)&Point[4] = v5;
  if ( WindowFromPoint(*(POINT *)Point) == a2 )
  {
    BlockInput(1);
    SystemMetrics = GetSystemMetrics(23);
    *(_QWORD *)Point = 0;
    v7 = SystemMetrics != 0 ? 16 : 4;
    v8 = SystemMetrics != 0 ? 8 : 2;
    GetCursorPos((LPPOINT)Point);
    *(_DWORD *)Point = v3 - *(_DWORD *)Point;
    pvParam_4 = 0;
    v21 = 0;
    *(_QWORD *)&Point[4] = (unsigned int)(v5 - *(_DWORD *)&Point[4]);
    if ( SystemParametersInfoW(3u, 0, &Point[8], 0) )
    {
      v2 = 1;
      v22 = 0;
      v23 = 0;
      if ( !v21 || SystemParametersInfoW(4u, 0, &v22, 0) )
      {
        v9 = GetSystemMetrics(43);
        v10 = (unsigned __int16)GetKeyState(17) >> 15;
        v11 = (unsigned __int16)GetKeyState(18) >> 15;
        v13 = (unsigned __int16)GetKeyState(16) >> 15;
        if ( v10 )
          SendKey(2, v12, 0x11u, v14);
        if ( v11 )
          SendKey(2, v12, 0x12u, v14);
        if ( v13 )
          SendKey(2, v12, 0x10u, v14);
        TickCount_0 = GetTickCount_0();
        *(_QWORD *)&pInputs.mi.dx = *(_QWORD *)Point;
        v28 = v8;
        *((_QWORD *)&pInputs.hi + 1) = v9 | 0x100000000LL;
        v27 = v9;
        v33 = v9;
        v40 = v9;
        pInputs.type = 0;
        pInputs.mi.dwExtraInfo = 0;
        v25 = 0;
        v38 = -*(_DWORD *)Point;
        v39 = -*(_DWORD *)&Point[4];
        pInputs.mi.time = TickCount_0;
        v30 = 0;
        v26 = 0;
        v29 = TickCount_0;
        v31 = 0;
        v34 = v7;
        v36 = 0;
        v32 = 0;
        v35 = TickCount_0;
        v37 = 0;
        v41 = 1;
        v43 = 0;
        v42 = TickCount_0;
        SendInput(4u, &pInputs, 40);
        if ( v10 )
          SendKey(0, v16, 0x11u, v17);
        if ( v11 )
          SendKey(0, v16, 0x12u, v17);
        if ( v13 )
          SendKey(0, v16, 0x10u, v17);
        if ( v21 )
          SystemParametersInfoW(4u, 0, &Point[8], 0);
      }
    }
    BlockInput(0);
  }
  return v2;
}

```

## disassembly

```asm
0x1801c4344  push    rbp
0x1801c4346  push    rbx
0x1801c4347  push    rsi
0x1801c4348  push    rdi
0x1801c4349  push    r12
0x1801c434b  push    r13
0x1801c434d  push    r14
0x1801c434f  push    r15
0x1801c4351  lea     rbp, [rsp-58h]
0x1801c4356  sub     rsp, 158h
0x1801c435d  mov     rax, cs:__security_cookie
0x1801c4364  xor     rax, rsp
0x1801c4367  mov     [rbp+90h+var_50], rax
0x1801c436b  mov     eax, [rcx+8]
0x1801c436e  mov     r9, rcx
0x1801c4371  mov     rbx, rdx
0x1801c4374  xor     r13d, r13d
0x1801c4377  cdq
0x1801c4378  mov     r12d, r13d
0x1801c437b  lea     ecx, [r13+2]
0x1801c437f  idiv    ecx
0x1801c4381  mov     edi, eax
0x1801c4383  mov     eax, [r9+0Ch]
0x1801c4387  add     edi, [r9]
0x1801c438a  cdq
0x1801c438b  idiv    ecx
0x1801c438d  mov     [rsp+190h+Point.x], edi
0x1801c4391  mov     esi, eax
0x1801c4393  add     esi, [r9+4]
0x1801c4397  mov     [rsp+190h+Point.y], esi
0x1801c439b  mov     rcx, qword ptr [rsp+190h+Point.x]; Point
0x1801c43a0  call    cs:__imp_WindowFromPoint
0x1801c43a6  cmp     rax, rbx
0x1801c43a9  jnz     loc_1801C45B7
0x1801c43af  lea     ebx, [r13+1]
0x1801c43b3  mov     ecx, ebx; fBlockIt
0x1801c43b5  call    cs:__imp_BlockInput
0x1801c43bb  lea     ecx, [rbx+16h]; nIndex
0x1801c43be  call    cs:__imp_GetSystemMetrics
0x1801c43c4  mov     ecx, eax
0x1801c43c6  mov     qword ptr [rsp+190h+Point.x], r13
0x1801c43cb  neg     eax
0x1801c43cd  sbb     r14d, r14d
0x1801c43d0  and     r14d, 0Ch
0x1801c43d4  add     r14d, 4
0x1801c43d8  neg     ecx
0x1801c43da  lea     rcx, [rsp+190h+Point]; lpPoint
0x1801c43df  sbb     r15d, r15d
0x1801c43e2  and     r15d, 6
0x1801c43e6  add     r15d, 2
0x1801c43ea  call    cs:__imp_GetCursorPos
0x1801c43f0  sub     edi, [rsp+190h+Point.x]
0x1801c43f4  lea     r8, [rsp+190h+pvParam]; pvParam
0x1801c43f9  sub     esi, [rsp+190h+Point.y]
0x1801c43fd  lea     ecx, [rbx+2]; uiAction
0x1801c4400  xor     eax, eax
0x1801c4402  mov     [rsp+190h+Point.x], edi
0x1801c4406  xor     r9d, r9d; fWinIni
0x1801c4409  mov     [rsp+190h+pvParam], rax
0x1801c440e  xor     edx, edx; uiParam
0x1801c4410  mov     [rsp+190h+var_160], eax
0x1801c4414  mov     [rsp+190h+Point.y], esi
0x1801c4418  call    cs:__imp_SystemParametersInfoW
0x1801c441e  test    eax, eax
0x1801c4420  jz      loc_1801C45AF
0x1801c4426  xor     eax, eax
0x1801c4428  mov     r12d, ebx
0x1801c442b  mov     [rsp+190h+var_158], rax
0x1801c4430  mov     [rsp+190h+var_150], eax
0x1801c4434  cmp     [rsp+190h+var_160], r13d
0x1801c4439  jz      short loc_1801C4456
0x1801c443b  xor     r9d, r9d; fWinIni
0x1801c443e  lea     r8, [rsp+190h+var_158]; pvParam
0x1801c4443  xor     edx, edx; uiParam
0x1801c4445  lea     ecx, [rbx+3]; uiAction
0x1801c4448  call    cs:__imp_SystemParametersInfoW
0x1801c444e  test    eax, eax
0x1801c4450  jz      loc_1801C45AF
0x1801c4456  mov     ecx, 2Bh ; '+'; nIndex
0x1801c445b  call    cs:__imp_GetSystemMetrics
0x1801c4461  mov     ecx, 11h; nVirtKey
0x1801c4466  mov     esi, eax
0x1801c4468  call    cs:__imp_GetKeyState
0x1801c446e  movzx   r13d, ax
0x1801c4472  mov     ecx, 12h; nVirtKey
0x1801c4477  shr     r13w, 0Fh
0x1801c447c  call    cs:__imp_GetKeyState
0x1801c4482  movzx   edi, ax
0x1801c4485  mov     ecx, 10h; nVirtKey
0x1801c448a  shr     di, 0Fh
0x1801c448e  call    cs:__imp_GetKeyState
0x1801c4494  movzx   ebx, ax
0x1801c4497  shr     bx, 0Fh
0x1801c449b  test    r13w, r13w
0x1801c449f  jz      short loc_1801C44AF
0x1801c44a1  mov     ecx, 2; int
0x1801c44a6  lea     r8d, [rcx+0Fh]; unsigned __int16
0x1801c44aa  call    ?SendKey@@YAHHHGG@Z; SendKey(int,int,ushort,ushort)
0x1801c44af  test    di, di
0x1801c44b2  jz      short loc_1801C44C2
0x1801c44b4  mov     ecx, 2; int
0x1801c44b9  lea     r8d, [rcx+10h]; unsigned __int16
0x1801c44bd  call    ?SendKey@@YAHHHGG@Z; SendKey(int,int,ushort,ushort)
0x1801c44c2  test    bx, bx
0x1801c44c5  jz      short loc_1801C44D5
0x1801c44c7  mov     ecx, 2; int
0x1801c44cc  lea     r8d, [rcx+0Eh]; unsigned __int16
0x1801c44d0  call    ?SendKey@@YAHHHGG@Z; SendKey(int,int,ushort,ushort)
0x1801c44d5  call    GetTickCount_0
0x1801c44da  mov     edx, [rsp+190h+Point.y]
0x1801c44de  xor     r8d, r8d
0x1801c44e1  mov     ecx, [rsp+190h+Point.x]
0x1801c44e5  mov     dword ptr [rsp+190h+pInputs.8], ecx
0x1801c44e9  neg     ecx
0x1801c44eb  mov     dword ptr [rsp+190h+pInputs.8+4], edx
0x1801c44ef  neg     edx
0x1801c44f1  mov     [rbp+90h+var_104], r15d
0x1801c44f5  xor     r15d, r15d
0x1801c44f8  mov     dword ptr [rsp+190h+pInputs.8+8], esi
0x1801c44fc  mov     [rbp+90h+var_108], esi
0x1801c44ff  mov     [rbp+90h+var_E0], esi
0x1801c4502  mov     [rbp+90h+var_B8], esi
0x1801c4505  lea     esi, [r15+4]
0x1801c4509  mov     [rsp+190h+pInputs.type], r8d
0x1801c450e  mov     qword ptr [rsp+190h+pInputs.8+18h], r8
0x1801c4513  mov     [rsp+190h+var_118], r8d
0x1801c4518  lea     r8d, [r15+28h]; cbSize
0x1801c451c  mov     [rbp+90h+var_C0], ecx
0x1801c451f  mov     ecx, esi; cInputs
0x1801c4521  mov     [rbp+90h+var_BC], edx
0x1801c4524  lea     rdx, [rsp+190h+pInputs]; pInputs
0x1801c4529  mov     dword ptr [rsp+190h+pInputs.8+0Ch], r12d
0x1801c452e  mov     dword ptr [rsp+190h+pInputs.8+10h], eax
0x1801c4532  mov     [rbp+90h+var_F8], r15
0x1801c4536  mov     [rbp+90h+var_110], r15
0x1801c453a  mov     [rbp+90h+var_100], eax
0x1801c453d  mov     [rbp+90h+var_F0], r15d
0x1801c4541  mov     [rbp+90h+var_DC], r14d
0x1801c4545  mov     [rbp+90h+var_D0], r15
0x1801c4549  mov     [rbp+90h+var_E8], r15
0x1801c454d  mov     [rbp+90h+var_D8], eax
0x1801c4550  mov     [rbp+90h+var_C8], r15d
0x1801c4554  mov     [rbp+90h+var_B4], r12d
0x1801c4558  mov     [rbp+90h+var_A8], r15
0x1801c455c  mov     [rbp+90h+var_B0], eax
0x1801c455f  call    cs:__imp_SendInput
0x1801c4565  test    r13w, r13w
0x1801c4569  jz      short loc_1801C4576
0x1801c456b  xor     ecx, ecx; int
0x1801c456d  lea     r8d, [r15+11h]; unsigned __int16
0x1801c4571  call    ?SendKey@@YAHHHGG@Z; SendKey(int,int,ushort,ushort)
0x1801c4576  test    di, di
0x1801c4579  jz      short loc_1801C4586
0x1801c457b  xor     ecx, ecx; int
0x1801c457d  lea     r8d, [rcx+12h]; unsigned __int16
0x1801c4581  call    ?SendKey@@YAHHHGG@Z; SendKey(int,int,ushort,ushort)
0x1801c4586  test    bx, bx
0x1801c4589  jz      short loc_1801C4596
0x1801c458b  xor     ecx, ecx; int
0x1801c458d  lea     r8d, [rcx+10h]; unsigned __int16
0x1801c4591  call    ?SendKey@@YAHHHGG@Z; SendKey(int,int,ushort,ushort)
0x1801c4596  cmp     [rsp+190h+var_160], r15d
0x1801c459b  jz      short loc_1801C45AF
0x1801c459d  xor     r9d, r9d; fWinIni
0x1801c45a0  lea     r8, [rsp+190h+pvParam]; pvParam
0x1801c45a5  xor     edx, edx; uiParam
0x1801c45a7  mov     ecx, esi; uiAction
0x1801c45a9  call    cs:__imp_SystemParametersInfoW
0x1801c45af  xor     ecx, ecx; fBlockIt
0x1801c45b1  call    cs:__imp_BlockInput
0x1801c45b7  mov     eax, r12d
0x1801c45ba  mov     rcx, [rbp+90h+var_50]
0x1801c45be  xor     rcx, rsp; StackCookie
0x1801c45c1  call    __security_check_cookie
0x1801c45c6  add     rsp, 158h
0x1801c45cd  pop     r15
0x1801c45cf  pop     r14
0x1801c45d1  pop     r13
0x1801c45d3  pop     r12
0x1801c45d5  pop     rdi
0x1801c45d6  pop     rsi
0x1801c45d7  pop     rbx
0x1801c45d8  pop     rbp
0x1801c45d9  retn
```
