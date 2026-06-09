# SendAllEventsB4

- ea: `0x1800048fc`
- end: `0x180004b2a`
- name: `SendAllEventsB4`
- size: `558`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18000484c`
- `0x180005090`
- `0x180005d4c`

## callees

- `0x180003dc0`
- `0x180003e98`
- `0x180003fdc`
- `0x1800048fc`
- `0x180004b30`
- `0x180004cc0`
- `0x180005044`
- `0x180005808`

## pseudocode

```c
__int64 __fastcall SendAllEventsB4(__int64 a1, int a2, int a3)
{
  unsigned int NextEvent; // eax
  __int64 v7; // rcx
  unsigned int v8; // edi
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // eax
  unsigned int v13; // edx
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  _DWORD *v18; // rdx
  int v19; // eax
  _DWORD *v20; // rcx
  int *v21; // rcx
  int v22; // eax

  NextEvent = GetNextEvent(a1);
  v8 = NextEvent;
  if ( *(_DWORD *)(v7 + 964) )
    return 256;
  *(_DWORD *)(v7 + 964) = 1;
  if ( a2 <= 0 )
    a2 = 0;
  if ( NextEvent == 256 )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)(a1 + 80);
      v11 = *(_DWORD *)(v10 + 4);
      if ( a2 < v11 + (a3 == 1) || *(_BYTE *)(a1 + 2093) )
        break;
      if ( a3 == 2 )
      {
        v12 = *(_DWORD *)(a1 + 24);
        v13 = *(_DWORD *)(a1 + 12);
        if ( v12 + v11 > v13 || v13 < *(_DWORD *)(a1 + 16) && v12 + v11 == v13 )
        {
          v8 = 260;
          SubtractAllTracks(a1, v13 - v12);
          *(_DWORD *)(a1 + 24) = *(_DWORD *)(a1 + 12);
          goto LABEL_51;
        }
      }
      v14 = *(_BYTE *)(v10 + 16);
      if ( v14 == -1 )
      {
        *(_QWORD *)(v10 + 40) = *(_QWORD *)(v10 + 24);
        HandleMetaEvent(a1, *(_QWORD *)(a1 + 80), a3);
        v15 = *(_QWORD *)(a1 + 80);
        if ( *(_DWORD *)v15 == 350 )
        {
          v16 = *(_QWORD *)(v15 + 40);
          if ( v16 )
            *(_QWORD *)(v15 + 24) = v16;
          v17 = 274;
          if ( a3 == 1 )
            v17 = 277;
          **(_DWORD **)(a1 + 80) = v17;
        }
      }
      else if ( v14 == -16 || v14 == -9 )
      {
        SendSysEx(a1);
        if ( *(_BYTE *)(a1 + 2093) )
          v8 = 261;
      }
      else if ( a3 == 2 && v11 >= 0 || (v14 & 0xF0) != 0x90 || !*(_BYTE *)(v10 + 18) )
      {
        SendMIDI(a1, *(_QWORD *)(a1 + 80));
      }
      v18 = *(_DWORD **)(a1 + 80);
      if ( !*v18 || *(_BYTE *)(a1 + 2093) || (unsigned int)(*v18 - 278) <= 2 )
      {
        v19 = v18[1];
        if ( v19 > 0 )
        {
          *(_DWORD *)(a1 + 24) += v19;
          a2 -= v19;
          SubtractAllTracks(a1, (unsigned int)v18[1]);
        }
      }
      v20 = *(_DWORD **)(a1 + 80);
      if ( !*v20 && !v20[14] && !*(_BYTE *)(a1 + 2093) )
        FillInNextTrack((__int64)v20);
      v21 = *(int **)(a1 + 80);
      if ( *v21 == 350 )
      {
        v22 = 270;
        if ( a3 == 1 )
          v22 = 276;
        *v21 = v22;
      }
      if ( *(_BYTE *)(a1 + 2093) )
      {
        if ( v8 != 256 )
          goto LABEL_51;
      }
      else
      {
        v8 = GetNextEvent(a1);
        if ( v8 != 256 )
          goto LABEL_51;
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 80) + 56LL) )
          *(_DWORD *)(a1 + 20) = 0;
      }
    }
    if ( v8 == 256 && (unsigned int)AllTracksUnblocked(a1) )
    {
      *(_DWORD *)(a1 + 24) += a2;
      SubtractAllTracks(a1, (unsigned int)a2);
    }
  }
LABEL_51:
  *(_DWORD *)(a1 + 964) = 0;
  return v8;
}

```

## disassembly

```asm
0x1800048fc  push    rbx
0x1800048fe  push    rbp
0x1800048ff  push    rdi
0x180004900  push    r12
0x180004902  push    r14
0x180004904  push    r15
0x180004906  sub     rsp, 28h
0x18000490a  mov     r14d, r8d
0x18000490d  mov     ebp, edx
0x18000490f  mov     rbx, rcx
0x180004912  call    GetNextEvent
0x180004917  xor     r12d, r12d
0x18000491a  mov     edi, eax
0x18000491c  cmp     [rcx+3C4h], r12d
0x180004923  jz      short loc_18000492F
0x180004925  mov     eax, 100h
0x18000492a  jmp     loc_180004B1C
0x18000492f  test    ebp, ebp
0x180004931  mov     dword ptr [rcx+3C4h], 1
0x18000493b  cmovle  ebp, r12d
0x18000493f  cmp     eax, 100h
0x180004944  jnz     loc_180004B13
0x18000494a  cmp     r14d, 1
0x18000494e  mov     r15d, r12d
0x180004951  setz    r15b
0x180004955  mov     rcx, [rbx+50h]
0x180004959  mov     r8d, [rcx+4]
0x18000495d  lea     eax, [r8+r15]
0x180004961  cmp     ebp, eax
0x180004963  jl      loc_180004AF2
0x180004969  cmp     [rbx+82Dh], r12b
0x180004970  jnz     loc_180004AF2
0x180004976  cmp     r14d, 2
0x18000497a  jnz     short loc_18000499D
0x18000497c  mov     eax, [rbx+18h]
0x18000497f  mov     edx, [rbx+0Ch]
0x180004982  lea     r9d, [rax+r8]
0x180004986  cmp     r9d, edx
0x180004989  ja      loc_180004ADB
0x18000498f  cmp     edx, [rbx+10h]
0x180004992  jnb     short loc_18000499D
0x180004994  cmp     r9d, edx
0x180004997  jz      loc_180004ADB
0x18000499d  mov     al, [rcx+10h]
0x1800049a0  cmp     al, 0FFh
0x1800049a2  jnz     short loc_1800049EB
0x1800049a4  mov     rax, [rcx+18h]
0x1800049a8  mov     r8d, r14d
0x1800049ab  mov     [rcx+28h], rax
0x1800049af  mov     rcx, rbx
0x1800049b2  mov     rdx, [rbx+50h]
0x1800049b6  call    HandleMetaEvent
0x1800049bb  mov     rax, [rbx+50h]
0x1800049bf  cmp     dword ptr [rax], 15Eh
0x1800049c5  jnz     short loc_180004A2E
0x1800049c7  mov     rcx, [rax+28h]
0x1800049cb  test    rcx, rcx
0x1800049ce  jz      short loc_1800049D4
0x1800049d0  mov     [rax+18h], rcx
0x1800049d4  mov     rcx, [rbx+50h]
0x1800049d8  mov     eax, 112h
0x1800049dd  cmp     r14d, 1
0x1800049e1  lea     edx, [rax+3]
0x1800049e4  cmovz   eax, edx
0x1800049e7  mov     [rcx], eax
0x1800049e9  jmp     short loc_180004A2E
0x1800049eb  cmp     al, 0F0h
0x1800049ed  jz      short loc_180004A17
0x1800049ef  cmp     al, 0F7h
0x1800049f1  jz      short loc_180004A17
0x1800049f3  cmp     r14d, 2
0x1800049f7  jnz     short loc_1800049FE
0x1800049f9  test    r8d, r8d
0x1800049fc  jns     short loc_180004A0A
0x1800049fe  and     al, 0F0h
0x180004a00  cmp     al, 90h
0x180004a02  jnz     short loc_180004A0A
0x180004a04  cmp     [rcx+12h], r12b
0x180004a08  jnz     short loc_180004A2E
0x180004a0a  mov     rdx, rcx
0x180004a0d  mov     rcx, rbx
0x180004a10  call    SendMIDI
0x180004a15  jmp     short loc_180004A2E
0x180004a17  mov     rcx, rbx
0x180004a1a  call    SendSysEx
0x180004a1f  cmp     [rbx+82Dh], r12b
0x180004a26  mov     eax, 105h
0x180004a2b  cmovnz  edi, eax
0x180004a2e  mov     rdx, [rbx+50h]
0x180004a32  mov     eax, [rdx]
0x180004a34  test    eax, eax
0x180004a36  jz      short loc_180004A4B
0x180004a38  cmp     [rbx+82Dh], r12b
0x180004a3f  jnz     short loc_180004A4B
0x180004a41  add     eax, 0FFFFFEEAh
0x180004a46  cmp     eax, 2
0x180004a49  ja      short loc_180004A62
0x180004a4b  mov     eax, [rdx+4]
0x180004a4e  test    eax, eax
0x180004a50  jle     short loc_180004A62
0x180004a52  add     [rbx+18h], eax
0x180004a55  sub     ebp, eax
0x180004a57  mov     edx, [rdx+4]
0x180004a5a  mov     rcx, rbx
0x180004a5d  call    SubtractAllTracks
0x180004a62  mov     rcx, [rbx+50h]
0x180004a66  cmp     [rcx], r12d
0x180004a69  jnz     short loc_180004A7F
0x180004a6b  cmp     [rcx+38h], r12d
0x180004a6f  jnz     short loc_180004A7F
0x180004a71  cmp     [rbx+82Dh], r12b
0x180004a78  jnz     short loc_180004A7F
0x180004a7a  call    FillInNextTrack
0x180004a7f  mov     rcx, [rbx+50h]
0x180004a83  cmp     dword ptr [rcx], 15Eh
0x180004a89  jnz     short loc_180004A9C
0x180004a8b  mov     eax, 10Eh
0x180004a90  cmp     r14d, 1
0x180004a94  lea     edx, [rax+6]
0x180004a97  cmovz   eax, edx
0x180004a9a  mov     [rcx], eax
0x180004a9c  cmp     [rbx+82Dh], r12b
0x180004aa3  jnz     short loc_180004ACD
0x180004aa5  mov     rcx, rbx
0x180004aa8  call    GetNextEvent
0x180004aad  mov     edi, eax
0x180004aaf  cmp     eax, 100h
0x180004ab4  jnz     short loc_180004B13
0x180004ab6  mov     rcx, [rbx+50h]
0x180004aba  cmp     [rcx+38h], r12d
0x180004abe  jz      loc_180004955
0x180004ac4  mov     [rbx+14h], r12d
0x180004ac8  jmp     loc_180004955
0x180004acd  cmp     edi, 100h
0x180004ad3  jz      loc_180004955
0x180004ad9  jmp     short loc_180004B13
0x180004adb  sub     edx, eax
0x180004add  mov     rcx, rbx
0x180004ae0  mov     edi, 104h
0x180004ae5  call    SubtractAllTracks
0x180004aea  mov     edx, [rbx+0Ch]
0x180004aed  mov     [rbx+18h], edx
0x180004af0  jmp     short loc_180004B13
0x180004af2  cmp     edi, 100h
0x180004af8  jnz     short loc_180004B13
0x180004afa  mov     rcx, rbx
0x180004afd  call    AllTracksUnblocked
0x180004b02  test    eax, eax
0x180004b04  jz      short loc_180004B13
0x180004b06  add     [rbx+18h], ebp
0x180004b09  mov     edx, ebp
0x180004b0b  mov     rcx, rbx
0x180004b0e  call    SubtractAllTracks
0x180004b13  mov     [rbx+3C4h], r12d
0x180004b1a  mov     eax, edi
0x180004b1c  add     rsp, 28h
0x180004b20  pop     r15
0x180004b22  pop     r14
0x180004b24  pop     r12
0x180004b26  pop     rdi
0x180004b27  pop     rbp
0x180004b28  pop     rbx
0x180004b29  retn
```
