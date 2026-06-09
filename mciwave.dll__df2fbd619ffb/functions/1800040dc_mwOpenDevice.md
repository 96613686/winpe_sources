# mwOpenDevice

- ea: `0x1800040dc`
- end: `0x180004310`
- name: `mwOpenDevice`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003614`

## callees

- `0x1800031c4`
- `0x1800040dc`
- `0x180005c29`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004281`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004281`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004164`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800042b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800042b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000428a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800042c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000428a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800042c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004276`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004276`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042a8`
- `WINMM!mciSetDriverData` at `0x1800042e1`
- `WINMM!mciSetDriverData` at `0x1800042e1`
- `WINMM!mmTaskCreate` at `0x180004259`
- `WINMM!mmTaskCreate` at `0x180004259`
- `WINMM!mmioOpenW` at `0x180004229`
- `WINMM!mmioOpenW` at `0x180004229`

## pseudocode

```c
__int64 __fastcall mwOpenDevice(int a1, __int64 a2, MCIDEVICEID a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // edi
  char *v8; // rax
  DWORD_PTR v9; // rsi
  _WORD *v10; // rbx
  __int64 v11; // rcx
  _WORD *v12; // rax
  __int64 v13; // rdx
  _WORD *v14; // rcx
  int v15; // eax
  void *v16; // rbx
  struct _MMIOINFO pmmioinfo; // [rsp+20h] [rbp-B8h] BYREF

  if ( (a1 & 0x10000) != 0 )
  {
    v5 = *(_DWORD *)(a2 + 36);
    if ( v5 > 9 || v5 < 2 )
      return 282;
  }
  else
  {
    v5 = wAudioSeconds;
  }
  v6 = 0;
  if ( (a1 & 0xA00) != 0 )
  {
    if ( (a1 & 0x100) != 0 )
      return 274;
    if ( (a1 & 0xA00) == 0xA00 )
      return 284;
    v8 = (char *)LocalAlloc(0x40u, 0x510u);
    v9 = (DWORD_PTR)v8;
    if ( !v8 )
      return 264;
    *(_DWORD *)v8 = a3;
    *((_DWORD *)v8 + 2) = 0;
    *((_DWORD *)v8 + 7) = 1;
    *(_QWORD *)(v8 + 36) = -1;
    *((_DWORD *)v8 + 3) = v5;
    *((_QWORD *)v8 + 11) = -1;
    v10 = *(_WORD **)(a2 + 20);
    if ( *v10 )
    {
      memset_0(&pmmioinfo, 0, sizeof(pmmioinfo));
      v11 = 2147483646;
      v12 = (_WORD *)(v9 + 256);
      v13 = 260;
      do
      {
        if ( !v11 )
          break;
        if ( !*v10 )
          break;
        *v12++ = *v10++;
        --v11;
        --v13;
      }
      while ( v13 );
      v14 = v12 - 1;
      if ( v13 )
        v14 = v12;
      *v14 = 0;
      if ( !v13 )
      {
        v6 = 268;
LABEL_30:
        LocalFree((HLOCAL)v9);
        return v6;
      }
      InitMMIOOpen(v9, &pmmioinfo);
      if ( !mmioOpenW((LPWSTR)(v9 + 256), &pmmioinfo, 0x100u) )
      {
        v6 = 304;
        goto LABEL_30;
      }
    }
    *(_DWORD *)(v9 + 32) = 1;
    if ( mmTaskCreate(mwTask, (HANDLE *)(v9 + 176), v9) )
    {
      v6 = 264;
      goto LABEL_30;
    }
    while ( 1 )
    {
      v15 = *(_DWORD *)(v9 + 32);
      if ( v15 != 1 )
        break;
      LeaveCriticalSection(&CritSec);
      Sleep(0xAu);
      EnterCriticalSection(&CritSec);
    }
    if ( v15 )
    {
      mciSetDriverData(a3, v9);
      return v6;
    }
    v6 = *(_DWORD *)(v9 + 140);
    v16 = *(void **)(v9 + 176);
    LeaveCriticalSection(&CritSec);
    WaitForSingleObject(v16, 0xFFFFFFFF);
    CloseHandle(v16);
    EnterCriticalSection(&CritSec);
    if ( v6 )
      goto LABEL_30;
  }
  return v6;
}

```

## disassembly

```asm
0x1800040dc  push    rbx
0x1800040de  push    rbp
0x1800040df  push    rsi
0x1800040e0  push    rdi
0x1800040e1  push    r14
0x1800040e3  push    r15
0x1800040e5  sub     rsp, 0A8h
0x1800040ec  mov     rax, cs:__security_cookie
0x1800040f3  xor     rax, rsp
0x1800040f6  mov     [rsp+0D8h+var_48], rax
0x1800040fe  mov     r14d, r8d
0x180004101  mov     rbp, rdx
0x180004104  bt      ecx, 10h
0x180004108  jb      short loc_180004112
0x18000410a  mov     ebx, cs:wAudioSeconds
0x180004110  jmp     short loc_180004127
0x180004112  mov     ebx, [rdx+24h]
0x180004115  cmp     ebx, 9
0x180004118  ja      loc_1800042E9
0x18000411e  cmp     ebx, 2
0x180004121  jb      loc_1800042E9
0x180004127  xor     r15d, r15d
0x18000412a  mov     eax, ecx
0x18000412c  mov     edx, 0A00h
0x180004131  mov     edi, r15d
0x180004134  and     eax, edx
0x180004136  jz      loc_1800042EE
0x18000413c  bt      ecx, 8
0x180004140  jnb     short loc_18000414C
0x180004142  mov     edi, 112h
0x180004147  jmp     loc_1800042EE
0x18000414c  cmp     eax, edx
0x18000414e  jnz     short loc_18000415A
0x180004150  mov     eax, 11Ch
0x180004155  jmp     loc_1800042F0
0x18000415a  mov     edx, 510h; uBytes
0x18000415f  mov     ecx, 40h ; '@'; uFlags
0x180004164  call    cs:__imp_LocalAlloc
0x18000416a  mov     rsi, rax
0x18000416d  test    rax, rax
0x180004170  jnz     short loc_18000417C
0x180004172  mov     edi, 108h
0x180004177  jmp     loc_1800042EE
0x18000417c  mov     [rax], r14d
0x18000417f  mov     [rax+8], r15d
0x180004183  mov     dword ptr [rax+1Ch], 1
0x18000418a  mov     qword ptr [rax+24h], 0FFFFFFFFFFFFFFFFh
0x180004192  mov     [rax+0Ch], ebx
0x180004195  mov     qword ptr [rax+58h], 0FFFFFFFFFFFFFFFFh
0x18000419d  mov     rbx, [rbp+14h]
0x1800041a1  cmp     [rbx], r15w
0x1800041a5  jz      loc_18000423E
0x1800041ab  xor     edx, edx; Val
0x1800041ad  lea     rcx, [rsp+0D8h+pmmioinfo]; void *
0x1800041b2  lea     r8d, [rdx+64h]; Size
0x1800041b6  call    memset_0
0x1800041bb  lea     rbp, [rsi+100h]
0x1800041c2  mov     ecx, 7FFFFFFEh
0x1800041c7  mov     rax, rbp
0x1800041ca  mov     edx, 104h
0x1800041cf  test    rcx, rcx
0x1800041d2  jz      short loc_1800041F3
0x1800041d4  movzx   r8d, word ptr [rbx]
0x1800041d8  test    r8w, r8w
0x1800041dc  jz      short loc_1800041F3
0x1800041de  mov     [rax], r8w
0x1800041e2  add     rbx, 2
0x1800041e6  add     rax, 2
0x1800041ea  dec     rcx
0x1800041ed  sub     rdx, 1
0x1800041f1  jnz     short loc_1800041CF
0x1800041f3  test    rdx, rdx
0x1800041f6  lea     rcx, [rax-2]
0x1800041fa  cmovnz  rcx, rax
0x1800041fe  mov     [rcx], r15w
0x180004202  jnz     short loc_18000420E
0x180004204  mov     edi, 10Ch
0x180004209  jmp     loc_1800042D0
0x18000420e  lea     rdx, [rsp+0D8h+pmmioinfo]
0x180004213  mov     rcx, rsi
0x180004216  call    InitMMIOOpen
0x18000421b  mov     r8d, 100h; fdwOpen
0x180004221  lea     rdx, [rsp+0D8h+pmmioinfo]; pmmioinfo
0x180004226  mov     rcx, rbp; pszFileName
0x180004229  call    cs:__imp_mmioOpenW
0x18000422f  test    rax, rax
0x180004232  jnz     short loc_18000423E
0x180004234  mov     edi, 130h
0x180004239  jmp     loc_1800042D0
0x18000423e  lea     rbx, [rsi+0B0h]
0x180004245  mov     dword ptr [rsi+20h], 1
0x18000424c  mov     rdx, rbx; lph
0x18000424f  lea     rcx, mwTask; lpfn
0x180004256  mov     r8, rsi; dwInst
0x180004259  call    cs:__imp_mmTaskCreate
0x18000425f  test    eax, eax
0x180004261  jz      short loc_18000426A
0x180004263  mov     edi, 108h
0x180004268  jmp     short loc_1800042D0
0x18000426a  lea     rbp, CritSec
0x180004271  jmp     short loc_180004290
0x180004273  mov     rcx, rbp; lpCriticalSection
0x180004276  call    cs:__imp_LeaveCriticalSection
0x18000427c  mov     ecx, 0Ah; dwMilliseconds
0x180004281  call    cs:__imp_Sleep
0x180004287  mov     rcx, rbp; lpCriticalSection
0x18000428a  call    cs:__imp_EnterCriticalSection
0x180004290  mov     eax, [rsi+20h]
0x180004293  cmp     eax, 1
0x180004296  jz      short loc_180004273
0x180004298  test    eax, eax
0x18000429a  jnz     short loc_1800042DB
0x18000429c  mov     edi, [rsi+8Ch]
0x1800042a2  mov     rcx, rbp; lpCriticalSection
0x1800042a5  mov     rbx, [rbx]
0x1800042a8  call    cs:__imp_LeaveCriticalSection
0x1800042ae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800042b1  mov     rcx, rbx; hHandle
0x1800042b4  call    cs:__imp_WaitForSingleObject
0x1800042ba  mov     rcx, rbx; hObject
0x1800042bd  call    cs:__imp_CloseHandle
0x1800042c3  mov     rcx, rbp; lpCriticalSection
0x1800042c6  call    cs:__imp_EnterCriticalSection
0x1800042cc  test    edi, edi
0x1800042ce  jz      short loc_1800042EE
0x1800042d0  mov     rcx, rsi; hMem
0x1800042d3  call    cs:__imp_LocalFree
0x1800042d9  jmp     short loc_1800042EE
0x1800042db  mov     rdx, rsi; dwData
0x1800042de  mov     ecx, r14d; wDeviceID
0x1800042e1  call    cs:__imp_mciSetDriverData
0x1800042e7  jmp     short loc_1800042EE
0x1800042e9  mov     edi, 11Ah
0x1800042ee  mov     eax, edi
0x1800042f0  mov     rcx, [rsp+0D8h+var_48]
0x1800042f8  xor     rcx, rsp; StackCookie
0x1800042fb  call    __security_check_cookie
0x180004300  add     rsp, 0A8h
0x180004307  pop     r15
0x180004309  pop     r14
0x18000430b  pop     rdi
0x18000430c  pop     rsi
0x18000430d  pop     rbp
0x18000430e  pop     rbx
0x18000430f  retn
```
