# RecordFile

- ea: `0x180001860`
- end: `0x180001a9f`
- name: `RecordFile`
- size: `575`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180005170`

## callees

- `0x180001860`
- `0x180001df8`
- `0x180001fa4`
- `0x180002150`
- `0x180005b1c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001a6e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001a6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a63`
- `WINMM!waveInStart` at `0x180001878`
- `WINMM!waveInStart` at `0x180001878`
- `WINMM!waveInAddBuffer` at `0x180001954`
- `WINMM!waveInAddBuffer` at `0x180001954`

## pseudocode

```c
__int64 __fastcall RecordFile(__int64 a1)
{
  MMRESULT v2; // eax
  unsigned int v4; // edi
  char ***v5; // r14
  LPWAVEHDR *v6; // r15
  int v7; // edx
  int v8; // eax
  int v9; // esi
  unsigned int v10; // ecx
  char ***v11; // rax
  unsigned int v12; // ecx
  MMRESULT v13; // eax
  LPWAVEHDR *v14; // rax
  int v15; // ebp
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // esi
  DWORD v19; // ecx
  DWORD v20; // r8d
  char *v21; // rdx
  char ***v22; // rax

  v2 = waveInStart(*(HWAVEIN *)(a1 + 56));
  *(_DWORD *)(a1 + 140) = v2;
  if ( v2 )
    return 0;
  v4 = 0;
  v5 = (char ***)(a1 + 184);
  v6 = (LPWAVEHDR *)(a1 + 184);
  while ( 1 )
  {
    v7 = *(_DWORD *)(a1 + 4);
    if ( (v7 & 0x2000) != 0 && v4 )
    {
      v8 = TaskBlock();
      v9 = *(_DWORD *)(a1 + 4);
      v10 = v4 - 1;
      if ( v8 != 1024 )
        v10 = v4;
      v4 = v10;
      if ( (v9 & 0x100) == 0 )
      {
        *(_DWORD *)(a1 + 136) = mwGetLevel(a1, **v5, *((unsigned int *)*v5 + 3));
        *(_DWORD *)(a1 + 4) = v9 | 0x10;
      }
      v11 = v5++;
      if ( (unsigned __int64)v11 >= a1 + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 144) + 22) )
        v5 = (char ***)(a1 + 184);
      goto LABEL_48;
    }
    if ( (v7 & 0x100) != 0 || v4 >= *(_DWORD *)(a1 + 144) )
      break;
    if ( (*(_DWORD *)(a1 + 4) & 0x2000) != 0 )
    {
      v12 = 64;
    }
    else
    {
      v12 = *(_DWORD *)(a1 + 72) - *(_DWORD *)(a1 + 64);
      if ( *(_DWORD *)(a1 + 148) < v12 )
        v12 = *(_DWORD *)(a1 + 148);
    }
    (*v6)->dwBufferLength = v12;
    (*v6)->dwFlags &= 0xFFFFFFF2;
    v13 = waveInAddBuffer(*(HWAVEIN *)(a1 + 56), *v6, 0x30u);
    *(_DWORD *)(a1 + 140) = v13;
    if ( v13 )
      goto LABEL_50;
    ++v4;
    v14 = v6++;
    if ( (unsigned __int64)v14 >= a1 + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 144) + 22) )
      v6 = (LPWAVEHDR *)(a1 + 184);
LABEL_48:
    LeaveCriticalSection(&CritSec);
    Sleep(0xAu);
    EnterCriticalSection(&CritSec);
  }
  if ( !v4 )
  {
    if ( (v7 & 0x100) == 0 || (v7 & 0x1000) != 0 )
      goto LABEL_50;
    *(_DWORD *)(a1 + 4) = (*(_DWORD *)(a1 + 4) | ((*(_DWORD *)(a1 + 4) & 0x400) != 0 ? 2 : 4)) & 0xFFFFFEFF;
    goto LABEL_48;
  }
  v15 = 0;
  while ( !v15 )
  {
    v16 = TaskBlock();
    v17 = *(_DWORD *)(a1 + 72);
    v18 = v4 - 1;
    if ( v16 != 1024 )
      v18 = v4;
    if ( v17 == *(_DWORD *)(a1 + 64) )
    {
      v4 = v18;
      break;
    }
    if ( (*(_DWORD *)(a1 + 4) & 0x2000) == 0 )
    {
      v19 = v17 - *(_DWORD *)(a1 + 64);
      v20 = *((_DWORD *)*v5 + 3);
      v21 = **v5;
      if ( (*(_BYTE *)(a1 + 4) & 2) != 0 )
      {
        if ( v20 >= v19 )
          v20 = v19;
        if ( !mwInsert(a1, v21, v20) )
          v15 = 1;
      }
      else
      {
        if ( v20 >= v19 )
          v20 = v19;
        if ( !mwOverWrite(a1, v21, v20) )
          v15 = 1;
      }
    }
    v4 = v18;
    v22 = v5++;
    if ( (unsigned __int64)v22 >= a1 + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 144) + 22) )
      v5 = (char ***)(a1 + 184);
    if ( ((_BYTE)(*v5)[3] & 1) == 0 || !v18 )
    {
      if ( v15 )
        break;
      goto LABEL_48;
    }
  }
LABEL_50:
  *(_DWORD *)(a1 + 4) &= 0xFFFFFFF9;
  return v4;
}

```

## disassembly

```asm
0x180001860  push    rbx
0x180001862  push    rbp
0x180001863  push    rsi
0x180001864  push    rdi
0x180001865  push    r12
0x180001867  push    r13
0x180001869  push    r14
0x18000186b  push    r15
0x18000186d  sub     rsp, 28h
0x180001871  mov     rbx, rcx
0x180001874  mov     rcx, [rcx+38h]; hwi
0x180001878  call    cs:__imp_waveInStart
0x18000187e  mov     [rbx+8Ch], eax
0x180001884  test    eax, eax
0x180001886  jz      short loc_18000188F
0x180001888  xor     eax, eax
0x18000188a  jmp     loc_180001A8E
0x18000188f  lea     r12, [rbx+0B8h]
0x180001896  xor     edi, edi
0x180001898  mov     r14, r12
0x18000189b  mov     r15, r12
0x18000189e  lea     r13d, [rdi+1]
0x1800018a2  mov     edx, [rbx+4]
0x1800018a5  mov     eax, edx
0x1800018a7  and     eax, 2000h
0x1800018ac  jz      short loc_18000190C
0x1800018ae  test    edi, edi
0x1800018b0  jz      short loc_18000190C
0x1800018b2  call    TaskBlock
0x1800018b7  mov     esi, [rbx+4]
0x1800018ba  lea     ecx, [rdi-1]
0x1800018bd  cmp     eax, 400h
0x1800018c2  cmovnz  ecx, edi
0x1800018c5  mov     edi, ecx
0x1800018c7  bt      esi, 8
0x1800018cb  jb      short loc_1800018EB
0x1800018cd  mov     rdx, [r14]
0x1800018d0  mov     rcx, rbx
0x1800018d3  mov     r8d, [rdx+0Ch]
0x1800018d7  mov     rdx, [rdx]
0x1800018da  call    mwGetLevel
0x1800018df  or      esi, 10h
0x1800018e2  mov     [rbx+88h], eax
0x1800018e8  mov     [rbx+4], esi
0x1800018eb  mov     eax, [rbx+90h]
0x1800018f1  add     rax, 16h
0x1800018f5  lea     rcx, [rbx+rax*8]
0x1800018f9  mov     rax, r14
0x1800018fc  add     r14, 8
0x180001900  cmp     rax, rcx
0x180001903  cmovnb  r14, r12
0x180001907  jmp     loc_180001A5C
0x18000190c  mov     ecx, edx
0x18000190e  and     ecx, 100h
0x180001914  jnz     short loc_18000198C
0x180001916  cmp     edi, [rbx+90h]
0x18000191c  jnb     short loc_18000198C
0x18000191e  test    eax, eax
0x180001920  jz      short loc_180001929
0x180001922  mov     ecx, 40h ; '@'
0x180001927  jmp     short loc_18000193A
0x180001929  mov     eax, [rbx+94h]
0x18000192f  mov     ecx, [rbx+48h]
0x180001932  sub     ecx, [rbx+40h]
0x180001935  cmp     eax, ecx
0x180001937  cmovb   ecx, eax
0x18000193a  mov     rax, [r15]
0x18000193d  mov     r8d, 30h ; '0'; cbwh
0x180001943  mov     [rax+8], ecx
0x180001946  mov     rax, [r15]
0x180001949  and     dword ptr [rax+18h], 0FFFFFFF2h
0x18000194d  mov     rdx, [r15]; pwh
0x180001950  mov     rcx, [rbx+38h]; hwi
0x180001954  call    cs:__imp_waveInAddBuffer
0x18000195a  mov     [rbx+8Ch], eax
0x180001960  test    eax, eax
0x180001962  jnz     loc_180001A88
0x180001968  mov     eax, [rbx+90h]
0x18000196e  add     edi, r13d
0x180001971  add     rax, 16h
0x180001975  lea     rcx, [rbx+rax*8]
0x180001979  mov     rax, r15
0x18000197c  add     r15, 8
0x180001980  cmp     rax, rcx
0x180001983  cmovnb  r15, r12
0x180001987  jmp     loc_180001A5C
0x18000198c  test    edi, edi
0x18000198e  jz      loc_180001A38
0x180001994  xor     ebp, ebp
0x180001996  test    ebp, ebp
0x180001998  jnz     loc_180001A88
0x18000199e  call    TaskBlock
0x1800019a3  mov     ecx, [rbx+48h]
0x1800019a6  lea     esi, [rdi-1]
0x1800019a9  cmp     eax, 400h
0x1800019ae  cmovnz  esi, edi
0x1800019b1  cmp     ecx, [rbx+40h]
0x1800019b4  jz      loc_180001A86
0x1800019ba  test    dword ptr [rbx+4], 2000h
0x1800019c1  jnz     short loc_180001A03
0x1800019c3  mov     rax, [r14]
0x1800019c6  sub     ecx, [rbx+40h]
0x1800019c9  test    byte ptr [rbx+4], 2
0x1800019cd  mov     r8d, [rax+0Ch]
0x1800019d1  mov     rdx, [rax]; lpBuffer
0x1800019d4  jz      short loc_1800019EE
0x1800019d6  cmp     r8d, ecx
0x1800019d9  cmovnb  r8d, ecx; nNumberOfBytesToWrite
0x1800019dd  mov     rcx, rbx; int
0x1800019e0  call    mwInsert
0x1800019e5  test    eax, eax
0x1800019e7  jnz     short loc_180001A03
0x1800019e9  mov     ebp, r13d
0x1800019ec  jmp     short loc_180001A03
0x1800019ee  cmp     r8d, ecx
0x1800019f1  cmovnb  r8d, ecx; nNumberOfBytesToWrite
0x1800019f5  mov     rcx, rbx; int
0x1800019f8  call    mwOverWrite
0x1800019fd  test    eax, eax
0x1800019ff  cmovz   ebp, r13d
0x180001a03  mov     eax, [rbx+90h]
0x180001a09  mov     edi, esi
0x180001a0b  add     rax, 16h
0x180001a0f  lea     rcx, [rbx+rax*8]
0x180001a13  mov     rax, r14
0x180001a16  add     r14, 8
0x180001a1a  cmp     rax, rcx
0x180001a1d  cmovnb  r14, r12
0x180001a21  mov     rax, [r14]
0x180001a24  test    [rax+18h], r13b
0x180001a28  jz      short loc_180001A32
0x180001a2a  test    esi, esi
0x180001a2c  jnz     loc_180001996
0x180001a32  test    ebp, ebp
0x180001a34  jnz     short loc_180001A88
0x180001a36  jmp     short loc_180001A5C
0x180001a38  test    ecx, ecx
0x180001a3a  jz      short loc_180001A88
0x180001a3c  bt      edx, 0Ch
0x180001a40  jb      short loc_180001A88
0x180001a42  mov     eax, edx
0x180001a44  and     eax, 400h
0x180001a49  neg     eax
0x180001a4b  sbb     ecx, ecx
0x180001a4d  and     ecx, 0FFFFFFFEh
0x180001a50  add     ecx, 4
0x180001a53  or      ecx, edx
0x180001a55  btr     ecx, 8
0x180001a59  mov     [rbx+4], ecx
0x180001a5c  lea     rcx, CritSec; lpCriticalSection
0x180001a63  call    cs:__imp_LeaveCriticalSection
0x180001a69  mov     ecx, 0Ah; dwMilliseconds
0x180001a6e  call    cs:__imp_Sleep
0x180001a74  lea     rcx, CritSec; lpCriticalSection
0x180001a7b  call    cs:__imp_EnterCriticalSection
0x180001a81  jmp     loc_1800018A2
0x180001a86  mov     edi, esi
0x180001a88  and     dword ptr [rbx+4], 0FFFFFFF9h
0x180001a8c  mov     eax, edi
0x180001a8e  add     rsp, 28h
0x180001a92  pop     r15
0x180001a94  pop     r14
0x180001a96  pop     r13
0x180001a98  pop     r12
0x180001a9a  pop     rdi
0x180001a9b  pop     rsi
0x180001a9c  pop     rbp
0x180001a9d  pop     rbx
0x180001a9e  retn
```
