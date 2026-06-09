# SNI_Spn::SpnInit(void)

- ea: `0x180182ee0`
- end: `0x1801832da`
- name: `?SpnInit@SNI_Spn@@SAKXZ`
- size: `1018`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180178220`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x180157620`
- `0x180182ee0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18018322f`
- `KERNEL32!FreeLibrary` at `0x18018323d`
- `KERNEL32!FreeLibrary` at `0x18018324b`
- `KERNEL32!FreeLibrary` at `0x18018322f`
- `KERNEL32!FreeLibrary` at `0x18018323d`
- `KERNEL32!FreeLibrary` at `0x18018324b`
- `KERNEL32!GetLastError` at `0x1801831b5`
- `KERNEL32!GetLastError` at `0x1801831b5`
- `KERNEL32!GetProcAddress` at `0x180182f99`
- `KERNEL32!GetProcAddress` at `0x180182fb7`
- `KERNEL32!GetProcAddress` at `0x180182fd5`
- `KERNEL32!GetProcAddress` at `0x180182ff3`
- `KERNEL32!GetProcAddress` at `0x180183011`
- `KERNEL32!GetProcAddress` at `0x18018302f`
- `KERNEL32!GetProcAddress` at `0x18018304d`
- `KERNEL32!GetProcAddress` at `0x180183083`
- `KERNEL32!GetProcAddress` at `0x1801830a1`
- `KERNEL32!GetProcAddress` at `0x1801830da`
- `KERNEL32!GetProcAddress` at `0x1801830fb`
- `KERNEL32!GetProcAddress` at `0x180182f99`
- `KERNEL32!GetProcAddress` at `0x180182fb7`
- `KERNEL32!GetProcAddress` at `0x180182fd5`
- `KERNEL32!GetProcAddress` at `0x180182ff3`
- `KERNEL32!GetProcAddress` at `0x180183011`
- `KERNEL32!GetProcAddress` at `0x18018302f`
- `KERNEL32!GetProcAddress` at `0x18018304d`
- `KERNEL32!GetProcAddress` at `0x180183083`
- `KERNEL32!GetProcAddress` at `0x1801830a1`
- `KERNEL32!GetProcAddress` at `0x1801830da`
- `KERNEL32!GetProcAddress` at `0x1801830fb`

## string_xrefs

- `0x1801830b8`: `secur32.dll`
- `0x180182f71`: `ntdsapi.dll`
- `0x180183061`: `netapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SNI_Spn::SpnInit(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v4; // ebp
  HMODULE v5; // rax
  HMODULE v6; // rbx
  HMODULE v7; // rsi
  HMODULE v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  HMODULE v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  HMODULE v16; // rax
  DWORD LastError; // r14d
  __int128 v19; // [rsp+40h] [rbp-88h]
  __int128 v20; // [rsp+50h] [rbp-78h]
  __int128 v21; // [rsp+60h] [rbp-68h]
  __int128 v22; // [rsp+70h] [rbp-58h]
  __int128 v23; // [rsp+80h] [rbp-48h]
  FARPROC ProcAddress; // [rsp+90h] [rbp-38h]
  __int64 v25; // [rsp+A0h] [rbp-28h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-20h] BYREF

  v26 = -1;
  v4 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266F08[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v26,
      off_180266F08[0],
      0);
  v5 = SNILoadSystemLibA("ntdsapi.dll", a2, a3, a4);
  v6 = v5;
  v7 = 0;
  v8 = 0;
  if ( !v5 )
    goto LABEL_23;
  *(_QWORD *)&v19 = GetProcAddress(v5, DsFunctionNames);
  if ( !(_QWORD)v19 )
    goto LABEL_23;
  *((_QWORD *)&v19 + 1) = GetProcAddress(v6, lpProcName);
  if ( !*((_QWORD *)&v19 + 1) )
    goto LABEL_23;
  *(_QWORD *)&v20 = GetProcAddress(v6, off_18024E190);
  if ( !(_QWORD)v20 )
    goto LABEL_23;
  *((_QWORD *)&v20 + 1) = GetProcAddress(v6, off_18024E198);
  if ( !*((_QWORD *)&v20 + 1) )
    goto LABEL_23;
  *(_QWORD *)&v21 = GetProcAddress(v6, off_18024E1A0);
  if ( !(_QWORD)v21 )
    goto LABEL_23;
  *((_QWORD *)&v21 + 1) = GetProcAddress(v6, off_18024E1A8);
  if ( !*((_QWORD *)&v21 + 1) )
    goto LABEL_23;
  *(_QWORD *)&v22 = GetProcAddress(v6, off_18024E1B0);
  if ( !(_QWORD)v22 )
    goto LABEL_23;
  v12 = SNILoadSystemLibA("netapi32.dll", v9, v10, v11);
  v7 = v12;
  if ( !v12 )
    goto LABEL_23;
  *((_QWORD *)&v22 + 1) = GetProcAddress(v12, off_18024E1B8);
  if ( *((_QWORD *)&v22 + 1)
    && (*(_QWORD *)&v23 = GetProcAddress(v7, "NetApiBufferFree"), (_QWORD)v23)
    && (v16 = SNILoadSystemLibA("secur32.dll", v13, v14, v15), (v8 = v16) != 0)
    && (*((_QWORD *)&v23 + 1) = GetProcAddress(v16, off_18024E1C0)) != 0
    && (ProcAddress = GetProcAddress(v8, off_18024E1C8)) != 0 )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265920[0] )
      bidTraceW(off_1802625D8[0], 162816, off_180265920[0], 0);
    gDsFunc = v19;
    xmmword_180254520 = v20;
    xmmword_180254530 = v21;
    xmmword_180254540 = v22;
    xmmword_180254550 = v23;
    qword_180254560 = (__int64)ProcAddress;
    ghSpnLib = v6;
    ghNetApiLib = v7;
    ghSecur = v8;
  }
  else
  {
LABEL_23:
    LastError = GetLastError();
    v25 = -1;
    if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266F10[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
        bidID,
        0,
        0,
        &v25,
        off_180266F10[0],
        0);
    if ( v6 )
      FreeLibrary(v6);
    if ( v7 )
      FreeLibrary(v7);
    if ( v8 )
      FreeLibrary(v8);
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v25);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265928[0] )
      bidTraceW(off_1802625E0[0], 179200, off_180265928[0], LastError);
    v4 = LastError;
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v26);
  return v4;
}

```

## disassembly

```asm
0x180182ee0  mov     r11, rsp
0x180182ee3  mov     [r11+8], rbx
0x180182ee7  mov     [r11+10h], rbp
0x180182eeb  mov     [r11+18h], rsi
0x180182eef  mov     [r11+20h], rdi
0x180182ef3  push    r14
0x180182ef5  sub     rsp, 0C0h
0x180182efc  mov     rax, cs:__security_cookie
0x180182f03  xor     rax, rsp
0x180182f06  mov     [rsp+0C8h+var_18], rax
0x180182f0e  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFFh
0x180182f16  mov     eax, cs:_bidGblFlags
0x180182f1c  and     eax, 20004h
0x180182f21  xor     ebp, ebp
0x180182f23  cmp     eax, 20004h
0x180182f28  jnz     short loc_180182F71
0x180182f2a  mov     rax, cs:off_180266F08; "<SNI_Spn::SpnInit|API|SNI> \n"
0x180182f31  test    rax, rax
0x180182f34  jz      short loc_180182F71
0x180182f36  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180182f3e  jz      short loc_180182F71
0x180182f40  mov     r10, cs:off_180248060
0x180182f47  mov     [rsp+0C8h+var_A0], rbp
0x180182f4c  mov     rax, cs:off_180266F08; "<SNI_Spn::SpnInit|API|SNI> \n"
0x180182f53  mov     [rsp+0C8h+var_A8], rax
0x180182f58  lea     r9, [r11-20h]
0x180182f5c  xor     r8d, r8d
0x180182f5f  xor     edx, edx
0x180182f61  mov     rcx, cs:_bidID
0x180182f68  mov     rax, r10
0x180182f6b  call    cs:__guard_dispatch_icall_fptr
0x180182f71  lea     rcx, aNtdsapiDll; "ntdsapi.dll"
0x180182f78  call    SNILoadSystemLibA
0x180182f7d  mov     rbx, rax
0x180182f80  mov     rsi, rbp
0x180182f83  mov     rdi, rbp
0x180182f86  test    rax, rax
0x180182f89  jz      loc_1801831B5
0x180182f8f  mov     rdx, cs:?DsFunctionNames@@3PAPEBDA; lpProcName
0x180182f96  mov     rcx, rax; hModule
0x180182f99  call    cs:__imp_GetProcAddress
0x180182f9f  mov     qword ptr [rsp+0C8h+var_88], rax
0x180182fa4  test    rax, rax
0x180182fa7  jz      loc_1801831B5
0x180182fad  mov     rdx, cs:lpProcName; lpProcName
0x180182fb4  mov     rcx, rbx; hModule
0x180182fb7  call    cs:__imp_GetProcAddress
0x180182fbd  mov     qword ptr [rsp+0C8h+var_88+8], rax
0x180182fc2  test    rax, rax
0x180182fc5  jz      loc_1801831B5
0x180182fcb  mov     rdx, cs:off_18024E190; lpProcName
0x180182fd2  mov     rcx, rbx; hModule
0x180182fd5  call    cs:__imp_GetProcAddress
0x180182fdb  mov     qword ptr [rsp+0C8h+var_78], rax
0x180182fe0  test    rax, rax
0x180182fe3  jz      loc_1801831B5
0x180182fe9  mov     rdx, cs:off_18024E198; lpProcName
0x180182ff0  mov     rcx, rbx; hModule
0x180182ff3  call    cs:__imp_GetProcAddress
0x180182ff9  mov     qword ptr [rsp+0C8h+var_78+8], rax
0x180182ffe  test    rax, rax
0x180183001  jz      loc_1801831B5
0x180183007  mov     rdx, cs:off_18024E1A0; lpProcName
0x18018300e  mov     rcx, rbx; hModule
0x180183011  call    cs:__imp_GetProcAddress
0x180183017  mov     qword ptr [rsp+0C8h+var_68], rax
0x18018301c  test    rax, rax
0x18018301f  jz      loc_1801831B5
0x180183025  mov     rdx, cs:off_18024E1A8; lpProcName
0x18018302c  mov     rcx, rbx; hModule
0x18018302f  call    cs:__imp_GetProcAddress
0x180183035  mov     qword ptr [rsp+0C8h+var_68+8], rax
0x18018303a  test    rax, rax
0x18018303d  jz      loc_1801831B5
0x180183043  mov     rdx, cs:off_18024E1B0; lpProcName
0x18018304a  mov     rcx, rbx; hModule
0x18018304d  call    cs:__imp_GetProcAddress
0x180183053  mov     qword ptr [rsp+0C8h+var_58], rax
0x180183058  test    rax, rax
0x18018305b  jz      loc_1801831B5
0x180183061  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x180183068  call    SNILoadSystemLibA
0x18018306d  mov     rsi, rax
0x180183070  test    rax, rax
0x180183073  jz      loc_1801831B5
0x180183079  mov     rdx, cs:off_18024E1B8; lpProcName
0x180183080  mov     rcx, rax; hModule
0x180183083  call    cs:__imp_GetProcAddress
0x180183089  mov     qword ptr [rsp+0C8h+var_58+8], rax
0x18018308e  test    rax, rax
0x180183091  jz      loc_1801831B5
0x180183097  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x18018309e  mov     rcx, rsi; hModule
0x1801830a1  call    cs:__imp_GetProcAddress
0x1801830a7  mov     qword ptr [rsp+0C8h+var_48], rax
0x1801830af  test    rax, rax
0x1801830b2  jz      loc_1801831B5
0x1801830b8  lea     rcx, aSecur32Dll; "secur32.dll"
0x1801830bf  call    SNILoadSystemLibA
0x1801830c4  mov     rdi, rax
0x1801830c7  test    rax, rax
0x1801830ca  jz      loc_1801831B5
0x1801830d0  mov     rdx, cs:off_18024E1C0; lpProcName
0x1801830d7  mov     rcx, rax; hModule
0x1801830da  call    cs:__imp_GetProcAddress
0x1801830e0  mov     qword ptr [rsp+0C8h+var_48+8], rax
0x1801830e8  test    rax, rax
0x1801830eb  jz      loc_1801831B5
0x1801830f1  mov     rdx, cs:off_18024E1C8; lpProcName
0x1801830f8  mov     rcx, rdi; hModule
0x1801830fb  call    cs:__imp_GetProcAddress
0x180183101  mov     [rsp+0C8h+var_38], rax
0x180183109  test    rax, rax
0x18018310c  jz      loc_1801831B5
0x180183112  mov     eax, cs:_bidGblFlags
0x180183118  and     eax, 20002h
0x18018311d  cmp     eax, 20002h
0x180183122  jnz     short loc_18018314B
0x180183124  mov     rax, cs:off_180265920; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x18018312b  test    rax, rax
0x18018312e  jz      short loc_18018314B
0x180183130  xor     r9d, r9d
0x180183133  mov     r8, cs:off_180265920; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x18018313a  mov     edx, 27C00h
0x18018313f  mov     rcx, cs:off_1802625D8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180183146  call    _bidTraceW
0x18018314b  movaps  xmm0, [rsp+0C8h+var_88]
0x180183150  movaps  cs:?gDsFunc@@3U_DsFunctionTable@@A, xmm0; _DsFunctionTable gDsFunc
0x180183157  movaps  xmm1, [rsp+0C8h+var_78]
0x18018315c  movaps  cs:xmmword_180254520, xmm1
0x180183163  movaps  xmm0, [rsp+0C8h+var_68]
0x180183168  movaps  cs:xmmword_180254530, xmm0
0x18018316f  movaps  xmm1, [rsp+0C8h+var_58]
0x180183174  movaps  cs:xmmword_180254540, xmm1
0x18018317b  movaps  xmm0, [rsp+0C8h+var_48]
0x180183183  movaps  cs:xmmword_180254550, xmm0
0x18018318a  movsd   xmm1, [rsp+0C8h+var_38]
0x180183193  movsd   cs:qword_180254560, xmm1
0x18018319b  mov     cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * ghSpnLib
0x1801831a2  mov     cs:?ghNetApiLib@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * ghNetApiLib
0x1801831a9  mov     cs:?ghSecur@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghSecur
0x1801831b0  jmp     loc_18018329C
0x1801831b5  call    cs:__imp_GetLastError
0x1801831bb  mov     r14d, eax
0x1801831be  mov     [rsp+0C8h+var_28], 0FFFFFFFFFFFFFFFFh
0x1801831ca  mov     eax, cs:_bidGblFlags
0x1801831d0  and     eax, 20004h
0x1801831d5  cmp     eax, 20004h
0x1801831da  jnz     short loc_180183227
0x1801831dc  mov     rax, cs:off_180266F10; "<SNI_Spn::DoSpnTerminate|API|SNI> \n"
0x1801831e3  test    rax, rax
0x1801831e6  jz      short loc_180183227
0x1801831e8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801831f0  jz      short loc_180183227
0x1801831f2  mov     r10, cs:off_180248060
0x1801831f9  mov     [rsp+0C8h+var_A0], rbp
0x1801831fe  mov     rax, cs:off_180266F10; "<SNI_Spn::DoSpnTerminate|API|SNI> \n"
0x180183205  mov     [rsp+0C8h+var_A8], rax
0x18018320a  lea     r9, [rsp+0C8h+var_28]
0x180183212  xor     r8d, r8d
0x180183215  xor     edx, edx
0x180183217  mov     rcx, cs:_bidID
0x18018321e  mov     rax, r10
0x180183221  call    cs:__guard_dispatch_icall_fptr
0x180183227  test    rbx, rbx
0x18018322a  jz      short loc_180183235
0x18018322c  mov     rcx, rbx; hLibModule
0x18018322f  call    cs:__imp_FreeLibrary
0x180183235  test    rsi, rsi
0x180183238  jz      short loc_180183243
0x18018323a  mov     rcx, rsi; hLibModule
0x18018323d  call    cs:__imp_FreeLibrary
0x180183243  test    rdi, rdi
0x180183246  jz      short loc_180183252
0x180183248  mov     rcx, rdi; hLibModule
0x18018324b  call    cs:__imp_FreeLibrary
0x180183251  nop
0x180183252  lea     rcx, [rsp+0C8h+var_28]; this
0x18018325a  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18018325f  nop
0x180183260  mov     eax, cs:_bidGblFlags
0x180183266  and     eax, 20002h
0x18018326b  cmp     eax, 20002h
0x180183270  jnz     short loc_180183299
0x180183272  mov     rax, cs:off_180265928; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x180183279  test    rax, rax
0x18018327c  jz      short loc_180183299
0x18018327e  mov     r9d, r14d
0x180183281  mov     r8, cs:off_180265928; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x180183288  mov     edx, 2BC00h
0x18018328d  mov     rcx, cs:off_1802625E0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180183294  call    _bidTraceW
0x180183299  mov     ebp, r14d
0x18018329c  lea     rcx, [rsp+0C8h+var_20]; this
0x1801832a4  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801832a9  nop
0x1801832aa  mov     eax, ebp
0x1801832ac  mov     rcx, [rsp+0C8h+var_18]
0x1801832b4  xor     rcx, rsp; StackCookie
0x1801832b7  call    __security_check_cookie
0x1801832bc  lea     r11, [rsp+0C8h+var_8]
0x1801832c4  mov     rbx, [r11+10h]
0x1801832c8  mov     rbp, [r11+18h]
0x1801832cc  mov     rsi, [r11+20h]
0x1801832d0  mov     rdi, [r11+28h]
0x1801832d4  mov     rsp, r11
0x1801832d7  pop     r14
0x1801832d9  retn
```
