# _CreateOleDC(tagDVTARGETDEVICE *)

- ea: `0x18002517c`
- end: `0x1800254ae`
- name: `?_CreateOleDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z`
- size: `818`
- prototype: `HDC __fastcall(struct tagDVTARGETDEVICE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180024c60`

## callees

- `0x18000c02c`
- `0x18000d170`
- `0x18000d24c`
- `0x180013b20`
- `0x18002517c`
- `0x180075c42`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!free` at `0x180025464`
- `msvcrt!free` at `0x180025464`
- `KERNEL32!lstrlenW` at `0x180025210`
- `KERNEL32!lstrlenW` at `0x18002525f`
- `KERNEL32!lstrlenW` at `0x1800252a5`
- `KERNEL32!lstrlenW` at `0x180025210`
- `KERNEL32!lstrlenW` at `0x18002525f`
- `KERNEL32!lstrlenW` at `0x1800252a5`
- `GDI32!CreateDCA` at `0x1800251d8`
- `GDI32!CreateDCA` at `0x18002544e`
- `GDI32!CreateDCA` at `0x1800251d8`
- `GDI32!CreateDCA` at `0x18002544e`

## pseudocode

```c
HDC __fastcall _CreateOleDC(struct tagDVTARGETDEVICE *a1)
{
  char *v3; // r15
  const WCHAR *v4; // rdi
  const WCHAR *v5; // rsi
  const WCHAR *v6; // r14
  int v7; // ebx
  const CHAR *v8; // rdi
  int v9; // ebx
  const CHAR *v10; // rsi
  int v11; // ebx
  const CHAR *v12; // r14
  _OWORD *v13; // rax
  DEVMODEA *v14; // rbx
  HDC DCA; // rdi
  __int128 v16; // xmm1
  size_t v17; // r8
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  CHAR v26[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B0h]
  __int128 v28; // [rsp+60h] [rbp-A0h]
  __m256i v29; // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+90h] [rbp-70h]
  _BYTE v31[60]; // [rsp+A0h] [rbp-60h]
  LPCSTR pszPort[18]; // [rsp+E0h] [rbp-20h] BYREF
  LPCSTR pwszDevice[18]; // [rsp+170h] [rbp+70h] BYREF
  LPCSTR pwszDriver[18]; // [rsp+200h] [rbp+100h] BYREF

  memset_0(v26, 0, 0x9Cu);
  if ( !a1 )
    return CreateDCA("DISPLAY", 0, 0, 0);
  if ( a1->tdExtDevmodeOffset )
    v3 = (char *)a1 + a1->tdExtDevmodeOffset;
  else
    v3 = 0;
  v4 = (const WCHAR *)((char *)a1 + a1->tdDriverNameOffset);
  v5 = (const WCHAR *)((char *)a1 + a1->tdDeviceNameOffset);
  v6 = (const WCHAR *)((char *)a1 + a1->tdPortNameOffset);
  v7 = 2 * lstrlenW(v4) + 2;
  TempBuffer::TempBuffer((TempBuffer *)pwszDriver, v7);
  HHWideCharToMultiByte(0, 0, v4, -1, (LPSTR)pwszDriver[0], v7, 0, 0);
  v8 = pwszDriver[0];
  v9 = 2 * lstrlenW(v5) + 2;
  TempBuffer::TempBuffer((TempBuffer *)pwszDevice, v9);
  HHWideCharToMultiByte(0, 0, v5, -1, (LPSTR)pwszDevice[0], v9, 0, 0);
  v10 = pwszDevice[0];
  v11 = 2 * lstrlenW(v6) + 2;
  TempBuffer::TempBuffer((TempBuffer *)pszPort, v11);
  HHWideCharToMultiByte(0, 0, v6, -1, (LPSTR)pszPort[0], v11, 0, 0);
  v12 = pszPort[0];
  if ( !v3 )
  {
    v14 = 0;
LABEL_14:
    DCA = CreateDCA(v8, v10, v12, v14);
    if ( v14 != (DEVMODEA *)v26 )
      free(v14);
    goto LABEL_16;
  }
  HHWideCharToMultiByte(0, 0, (const unsigned __int16 *)v3, -1, v26, 32, 0, 0);
  v28 = *((_OWORD *)v3 + 4);
  *(_OWORD *)v29.m256i_i8 = *((_OWORD *)v3 + 5);
  *(__int64 *)((char *)&v29.m256i_i64[1] + 6) = *(_QWORD *)(v3 + 94);
  HHWideCharToMultiByte(0, 0, (const unsigned __int16 *)v3 + 51, -1, &v29.m256i_i8[22], 32, 0, 0);
  *(_OWORD *)&v31[6] = *(_OWORD *)(v3 + 166);
  *(_OWORD *)&v31[22] = *(_OWORD *)(v3 + 182);
  *(_OWORD *)&v31[38] = *(_OWORD *)(v3 + 198);
  *(_QWORD *)&v31[52] = *(_QWORD *)(v3 + 212);
  if ( !*((_WORD *)v3 + 35) )
  {
    v14 = (DEVMODEA *)v26;
    goto LABEL_12;
  }
  v13 = lcCalloc((unsigned int)*((unsigned __int16 *)v3 + 35) + 156);
  v14 = (DEVMODEA *)v13;
  if ( v13 )
  {
    v16 = v27;
    v17 = *((unsigned __int16 *)v3 + 35);
    *v13 = *(_OWORD *)v26;
    v18 = v28;
    v13[1] = v16;
    v19 = *(_OWORD *)v29.m256i_i8;
    v13[2] = v18;
    v20 = *(_OWORD *)&v29.m256i_u64[2];
    v13[3] = v19;
    v21 = v30;
    v13[4] = v20;
    v22 = *(_OWORD *)v31;
    v13[5] = v21;
    v23 = *(_OWORD *)&v31[16];
    v13[6] = v22;
    v24 = *(_OWORD *)&v31[32];
    v13[7] = v23;
    v25 = *(_OWORD *)&v31[44];
    v13[8] = v24;
    *(_OWORD *)((char *)v13 + 140) = v25;
    memcpy_0((char *)v13 + 156, v3 + 220, v17);
LABEL_12:
    v14->dmSize = 156;
    goto LABEL_14;
  }
  DCA = 0;
LABEL_16:
  TempBuffer::~TempBuffer((TempBuffer *)pszPort);
  TempBuffer::~TempBuffer((TempBuffer *)pwszDevice);
  TempBuffer::~TempBuffer((TempBuffer *)pwszDriver);
  return DCA;
}

```

## disassembly

```asm
0x18002517c  push    rbp
0x18002517e  push    rbx
0x18002517f  push    rsi
0x180025180  push    rdi
0x180025181  push    r12
0x180025183  push    r13
0x180025185  push    r14
0x180025187  push    r15
0x180025189  lea     rbp, [rsp-1A8h]
0x180025191  sub     rsp, 2A8h
0x180025198  mov     rax, cs:__security_cookie
0x18002519f  xor     rax, rsp
0x1800251a2  mov     [rbp+1E0h+var_50], rax
0x1800251a9  mov     rbx, rcx
0x1800251ac  mov     r13d, 9Ch
0x1800251b2  mov     r8d, r13d; Size
0x1800251b5  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1800251ba  xor     edx, edx; Val
0x1800251bc  call    memset_0
0x1800251c1  xor     r12d, r12d
0x1800251c4  test    rbx, rbx
0x1800251c7  jnz     short loc_1800251E3
0x1800251c9  xor     r9d, r9d; pdm
0x1800251cc  lea     rcx, pszDriver; "DISPLAY"
0x1800251d3  xor     r8d, r8d; pszPort
0x1800251d6  xor     edx, edx; pwszDevice
0x1800251d8  call    cs:__imp_CreateDCA
0x1800251de  jmp     loc_18002548B
0x1800251e3  cmp     [rbx+0Ah], r12w
0x1800251e8  jnz     short loc_1800251EF
0x1800251ea  mov     r15, r12
0x1800251ed  jmp     short loc_1800251F7
0x1800251ef  movzx   r15d, word ptr [rbx+0Ah]
0x1800251f4  add     r15, rbx
0x1800251f7  movzx   edi, word ptr [rbx+4]
0x1800251fb  movzx   esi, word ptr [rbx+6]
0x1800251ff  add     rdi, rbx
0x180025202  movzx   r14d, word ptr [rbx+8]
0x180025207  mov     rcx, rdi; lpString
0x18002520a  add     rsi, rbx
0x18002520d  add     r14, rbx
0x180025210  call    cs:__imp_lstrlenW
0x180025216  lea     rcx, [rbp+1E0h+pwszDriver]; this
0x18002521d  lea     ebx, ds:2[rax*2]
0x180025224  mov     edx, ebx; unsigned int
0x180025226  call    ??0TempBuffer@@QEAA@K@Z; TempBuffer::TempBuffer(ulong)
0x18002522b  mov     rax, [rbp+1E0h+pwszDriver]
0x180025232  or      r9d, 0FFFFFFFFh; int
0x180025236  mov     [rsp+2E0h+var_2A8], r12; LPBOOL
0x18002523b  mov     r8, rdi; unsigned __int16 *
0x18002523e  mov     [rsp+2E0h+var_2B0], r12; LPCCH
0x180025243  xor     edx, edx; unsigned int
0x180025245  mov     [rsp+2E0h+var_2B8], ebx; int
0x180025249  xor     ecx, ecx; unsigned int
0x18002524b  mov     [rsp+2E0h+var_2C0], rax; LPSTR
0x180025250  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180025255  mov     rdi, [rbp+1E0h+pwszDriver]
0x18002525c  mov     rcx, rsi; lpString
0x18002525f  call    cs:__imp_lstrlenW
0x180025265  lea     rcx, [rbp+1E0h+pwszDevice]; this
0x180025269  lea     ebx, ds:2[rax*2]
0x180025270  mov     edx, ebx; unsigned int
0x180025272  call    ??0TempBuffer@@QEAA@K@Z; TempBuffer::TempBuffer(ulong)
0x180025277  mov     rax, [rbp+1E0h+pwszDevice]
0x18002527b  or      r9d, 0FFFFFFFFh; int
0x18002527f  mov     [rsp+2E0h+var_2A8], r12; LPBOOL
0x180025284  mov     r8, rsi; unsigned __int16 *
0x180025287  mov     [rsp+2E0h+var_2B0], r12; LPCCH
0x18002528c  xor     edx, edx; unsigned int
0x18002528e  mov     [rsp+2E0h+var_2B8], ebx; int
0x180025292  xor     ecx, ecx; unsigned int
0x180025294  mov     [rsp+2E0h+var_2C0], rax; LPSTR
0x180025299  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18002529e  mov     rsi, [rbp+1E0h+pwszDevice]
0x1800252a2  mov     rcx, r14; lpString
0x1800252a5  call    cs:__imp_lstrlenW
0x1800252ab  lea     rcx, [rbp+1E0h+pszPort]; this
0x1800252af  lea     ebx, ds:2[rax*2]
0x1800252b6  mov     edx, ebx; unsigned int
0x1800252b8  call    ??0TempBuffer@@QEAA@K@Z; TempBuffer::TempBuffer(ulong)
0x1800252bd  mov     rax, [rbp+1E0h+pszPort]
0x1800252c1  or      r9d, 0FFFFFFFFh; int
0x1800252c5  mov     [rsp+2E0h+var_2A8], r12; LPBOOL
0x1800252ca  mov     r8, r14; unsigned __int16 *
0x1800252cd  mov     [rsp+2E0h+var_2B0], r12; LPCCH
0x1800252d2  xor     edx, edx; unsigned int
0x1800252d4  mov     [rsp+2E0h+var_2B8], ebx; int
0x1800252d8  xor     ecx, ecx; unsigned int
0x1800252da  mov     [rsp+2E0h+var_2C0], rax; LPSTR
0x1800252df  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x1800252e4  mov     r14, [rbp+1E0h+pszPort]
0x1800252e8  test    r15, r15
0x1800252eb  jz      loc_18002543F
0x1800252f1  mov     [rsp+2E0h+var_2A8], r12; LPBOOL
0x1800252f6  lea     rax, [rsp+2E0h+var_2A0]
0x1800252fb  mov     [rsp+2E0h+var_2B0], r12; LPCCH
0x180025300  mov     ebx, 20h ; ' '
0x180025305  mov     [rsp+2E0h+var_2B8], ebx; int
0x180025309  or      r9d, 0FFFFFFFFh; int
0x18002530d  mov     r8, r15; unsigned __int16 *
0x180025310  mov     [rsp+2E0h+var_2C0], rax; LPSTR
0x180025315  xor     edx, edx; unsigned int
0x180025317  xor     ecx, ecx; unsigned int
0x180025319  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18002531e  movups  xmm0, xmmword ptr [r15+40h]
0x180025323  mov     [rsp+2E0h+var_2A8], r12; LPBOOL
0x180025328  lea     rax, [rbp+1E0h+var_25A]
0x18002532c  mov     [rsp+2E0h+var_2B0], r12; LPCCH
0x180025331  lea     r8, [r15+66h]; unsigned __int16 *
0x180025335  movaps  [rsp+2E0h+var_280], xmm0
0x18002533a  or      r9d, 0FFFFFFFFh; int
0x18002533e  movups  xmm1, xmmword ptr [r15+50h]
0x180025343  mov     [rsp+2E0h+var_2B8], ebx; int
0x180025347  xor     edx, edx; unsigned int
0x180025349  xor     ecx, ecx; unsigned int
0x18002534b  mov     [rsp+2E0h+var_2C0], rax; LPSTR
0x180025350  movaps  [rsp+2E0h+var_270], xmm1
0x180025355  movsd   xmm0, qword ptr [r15+5Eh]
0x18002535b  movsd   qword ptr [rsp+2E0h+var_270+0Eh], xmm0
0x180025361  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180025366  movups  xmm0, xmmword ptr [r15+0A6h]
0x18002536e  movups  [rbp+1E0h+var_23A], xmm0
0x180025372  movups  xmm1, xmmword ptr [r15+0B6h]
0x18002537a  movups  [rbp+1E0h+var_22A], xmm1
0x18002537e  movups  xmm0, xmmword ptr [r15+0C6h]
0x180025386  movups  [rbp+1E0h+var_21A], xmm0
0x18002538a  movsd   xmm1, qword ptr [r15+0D4h]
0x180025393  movsd   qword ptr [rbp+1E0h+var_21A+0Eh], xmm1
0x180025398  cmp     [r15+46h], r12w
0x18002539d  jz      loc_180025433
0x1800253a3  movzx   ecx, word ptr [r15+46h]
0x1800253a8  add     ecx, r13d; int
0x1800253ab  call    ?lcCalloc@@YAPEAXH@Z; lcCalloc(int)
0x1800253b0  mov     rbx, rax
0x1800253b3  test    rax, rax
0x1800253b6  jnz     short loc_1800253C0
0x1800253b8  mov     rdi, r12
0x1800253bb  jmp     loc_18002546A
0x1800253c0  movaps  xmm0, xmmword ptr [rsp+2E0h+var_2A0]
0x1800253c5  lea     rdx, [r15+0DCh]; Src
0x1800253cc  movaps  xmm1, [rsp+2E0h+var_290]
0x1800253d1  lea     rcx, [rax+9Ch]; void *
0x1800253d8  movzx   r8d, word ptr [r15+46h]; Size
0x1800253dd  movups  xmmword ptr [rax], xmm0
0x1800253e0  movaps  xmm0, [rsp+2E0h+var_280]
0x1800253e5  movups  xmmword ptr [rax+10h], xmm1
0x1800253e9  movaps  xmm1, [rsp+2E0h+var_270]
0x1800253ee  movups  xmmword ptr [rax+20h], xmm0
0x1800253f2  movaps  xmm0, xmmword ptr [rbp-80h]
0x1800253f6  movups  xmmword ptr [rax+30h], xmm1
0x1800253fa  movaps  xmm1, [rbp+1E0h+var_250]
0x1800253fe  movups  xmmword ptr [rax+40h], xmm0
0x180025402  movaps  xmm0, xmmword ptr [rbp-60h]
0x180025406  movups  xmmword ptr [rax+50h], xmm1
0x18002540a  movaps  xmm1, [rbp+1E0h+var_23A+0Ah]
0x18002540e  movups  xmmword ptr [rax+60h], xmm0
0x180025412  movaps  xmm0, [rbp+1E0h+var_22A+0Ah]
0x180025416  movups  xmmword ptr [rax+70h], xmm1
0x18002541a  movups  xmm1, [rbp+1E0h+var_21A+6]
0x18002541e  movups  xmmword ptr [rax+80h], xmm0
0x180025425  movups  xmmword ptr [rax+8Ch], xmm1
0x18002542c  call    memcpy_0
0x180025431  jmp     short loc_180025438
0x180025433  lea     rbx, [rsp+2E0h+var_2A0]
0x180025438  mov     [rbx+24h], r13w
0x18002543d  jmp     short loc_180025442
0x18002543f  mov     rbx, r12
0x180025442  mov     r9, rbx; pdm
0x180025445  mov     r8, r14; pszPort
0x180025448  mov     rdx, rsi; pwszDevice
0x18002544b  mov     rcx, rdi; pwszDriver
0x18002544e  call    cs:__imp_CreateDCA
0x180025454  mov     rdi, rax
0x180025457  lea     rax, [rsp+2E0h+var_2A0]
0x18002545c  cmp     rbx, rax
0x18002545f  jz      short loc_18002546A
0x180025461  mov     rcx, rbx; Block
0x180025464  call    cs:__imp_free
0x18002546a  lea     rcx, [rbp+1E0h+pszPort]; this
0x18002546e  call    ??1TempBuffer@@QEAA@XZ; TempBuffer::~TempBuffer(void)
0x180025473  lea     rcx, [rbp+1E0h+pwszDevice]; this
0x180025477  call    ??1TempBuffer@@QEAA@XZ; TempBuffer::~TempBuffer(void)
0x18002547c  lea     rcx, [rbp+1E0h+pwszDriver]; this
0x180025483  call    ??1TempBuffer@@QEAA@XZ; TempBuffer::~TempBuffer(void)
0x180025488  mov     rax, rdi
0x18002548b  mov     rcx, [rbp+1E0h+var_50]
0x180025492  xor     rcx, rsp; StackCookie
0x180025495  call    __security_check_cookie
0x18002549a  add     rsp, 2A8h
0x1800254a1  pop     r15
0x1800254a3  pop     r14
0x1800254a5  pop     r13
0x1800254a7  pop     r12
0x1800254a9  pop     rdi
0x1800254aa  pop     rsi
0x1800254ab  pop     rbx
0x1800254ac  pop     rbp
0x1800254ad  retn
```
