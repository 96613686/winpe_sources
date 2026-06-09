# directVideoColorConv_MultiThreads(uchar const *,uchar *,ulong,DIRECTCOLORCONVFRM *,uchar *,uchar *)

- ea: `0x18000630c`
- end: `0x1800064c3`
- name: `?directVideoColorConv_MultiThreads@@YA?AW4tagColorConvertStatus@@PEBEPEAEKPEAUDIRECTCOLORCONVFRM@@11@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64 *, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006260`
- `0x180009660`
- `0x18001faa0`

## callees

- `0x18000630c`
- `0x180006798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800063ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800063ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800063c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800063c8`

## pseudocode

```c
__int64 __fastcall directVideoColorConv_MultiThreads(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // rax
  __int64 v9; // r9
  __int64 v10; // rax
  unsigned int v11; // eax
  void *v12; // rcx
  __int64 v14; // r8
  int v15; // ecx
  __int64 v16; // rax

  v6 = *a4;
  v9 = a5;
  if ( (*(_DWORD *)(v6 + 16) == 1448433993 || *(_DWORD *)(v6 + 16) == 808596553)
    && (*(_BYTE *)(v6 + 8) & 1) != 0
    && (!a5 || !a6) )
  {
    return 6;
  }
  if ( *((_DWORD *)a4 + 6) )
  {
    if ( *((_DWORD *)a4 + 6) == 1 )
    {
      a4[5] = a1 + *((unsigned int *)a4 + 32);
      if ( !a5 )
        v9 = a1 + *((unsigned int *)a4 + 33);
      a4[6] = v9;
      if ( a6 )
        a4[7] = a6;
      else
        a4[7] = a1 + *((unsigned int *)a4 + 34);
    }
  }
  else
  {
    a4[4] = a1 + *((unsigned int *)a4 + 31);
  }
  if ( a3 )
    v10 = a2 + a3;
  else
    v10 = -1;
  a4[9] = v10;
  *((_DWORD *)a4 + 26) = 0;
  if ( !*((_DWORD *)a4 + 7) )
  {
    v14 = *((unsigned int *)a4 + 35);
    a4[8] = a2 + v14;
    if ( !a3 )
      goto LABEL_10;
    v15 = -*((_DWORD *)a4 + 3643);
    if ( *((int *)a4 + 3643) > 0 )
      v15 = *((_DWORD *)a4 + 3643);
    if ( (int)v14 + v15 <= a3 )
      goto LABEL_10;
    *((_DWORD *)a4 + 26) = 1;
    return 6;
  }
  if ( *((_DWORD *)a4 + 7) == 1 )
  {
    v16 = a2 + *((unsigned int *)a4 + 36);
    a4[10] = a2;
    a4[11] = v16;
    a4[12] = a2 + *((unsigned int *)a4 + 37);
  }
LABEL_10:
  v11 = *((_DWORD *)a4 + 3660);
  if ( v11 == 1 )
  {
    process0((struct DIRECTCOLORCONVFRM *)a4);
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)a4 + 3661, v11);
    ReleaseSemaphore((HANDLE)a4[*((int *)a4 + 3662) + 1836], *((_DWORD *)a4 + 3660), 0);
    v12 = (void *)a4[1838];
    *((_DWORD *)a4 + 3662) = 1 - *((_DWORD *)a4 + 3662);
    WaitForSingleObject(v12, 0xFFFFFFFF);
  }
  return *((_DWORD *)a4 + 26) != 0 ? 6 : 0;
}

```

## disassembly

```asm
0x18000630c  mov     [rsp+arg_0], rbx
0x180006311  push    rdi
0x180006312  sub     rsp, 20h
0x180006316  mov     rax, [r9]
0x180006319  xor     r11d, r11d
0x18000631c  mov     rbx, r9
0x18000631f  mov     r10d, r8d
0x180006322  mov     r8, [rsp+28h+arg_28]
0x180006327  mov     edi, 1
0x18000632c  mov     r9, [rsp+28h+arg_20]
0x180006331  cmp     dword ptr [rax+10h], 56555949h
0x180006338  jz      loc_180006484
0x18000633e  cmp     dword ptr [rax+10h], 30323449h
0x180006345  jz      loc_180006484
0x18000634b  cmp     [rbx+18h], r11d
0x18000634f  jnz     loc_180006422
0x180006355  mov     eax, [rbx+7Ch]
0x180006358  add     rax, rcx
0x18000635b  mov     [rbx+20h], rax
0x18000635f  test    r10d, r10d
0x180006362  jnz     short loc_1800063E3
0x180006364  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006368  mov     [rbx+48h], rax
0x18000636c  mov     [rbx+68h], r11d
0x180006370  cmp     [rbx+1Ch], r11d
0x180006374  jz      short loc_1800063EC
0x180006376  cmp     [rbx+1Ch], edi
0x180006379  jz      loc_180006461
0x18000637f  mov     eax, [rbx+3930h]
0x180006385  cmp     eax, edi
0x180006387  jz      loc_18000649D
0x18000638d  lock add [rbx+3934h], eax
0x180006394  movsxd  rcx, dword ptr [rbx+3938h]
0x18000639b  xor     r8d, r8d; lpPreviousCount
0x18000639e  mov     edx, [rbx+3930h]; lReleaseCount
0x1800063a4  mov     rcx, [rbx+rcx*8+3960h]; hSemaphore
0x1800063ac  call    cs:__imp_ReleaseSemaphore
0x1800063b2  sub     edi, [rbx+3938h]
0x1800063b8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800063bb  mov     rcx, [rbx+3970h]; hHandle
0x1800063c2  mov     [rbx+3938h], edi
0x1800063c8  call    cs:__imp_WaitForSingleObject
0x1800063ce  mov     eax, [rbx+68h]
0x1800063d1  neg     eax
0x1800063d3  sbb     eax, eax
0x1800063d5  and     eax, 6
0x1800063d8  mov     rbx, [rsp+28h+arg_0]
0x1800063dd  add     rsp, 20h
0x1800063e1  pop     rdi
0x1800063e2  retn
0x1800063e3  lea     rax, [rdx+r10]
0x1800063e7  jmp     loc_180006368
0x1800063ec  mov     r8d, [rbx+8Ch]
0x1800063f3  lea     rax, [rdx+r8]
0x1800063f7  mov     [rbx+40h], rax
0x1800063fb  test    r10d, r10d
0x1800063fe  jz      loc_18000637F
0x180006404  mov     eax, [rbx+38ECh]
0x18000640a  mov     ecx, eax
0x18000640c  neg     ecx
0x18000640e  cmovs   ecx, eax
0x180006411  add     ecx, r8d
0x180006414  cmp     ecx, r10d
0x180006417  jbe     loc_18000637F
0x18000641d  mov     [rbx+68h], edi
0x180006420  jmp     short loc_180006493
0x180006422  cmp     [rbx+18h], edi
0x180006425  jnz     loc_18000635F
0x18000642b  mov     eax, [rbx+80h]
0x180006431  add     rax, rcx
0x180006434  mov     [rbx+28h], rax
0x180006438  test    r9, r9
0x18000643b  jz      short loc_1800064B4
0x18000643d  mov     [rbx+30h], r9
0x180006441  test    r8, r8
0x180006444  jz      short loc_18000644F
0x180006446  mov     [rbx+38h], r8
0x18000644a  jmp     loc_18000635F
0x18000644f  mov     eax, [rbx+88h]
0x180006455  add     rax, rcx
0x180006458  mov     [rbx+38h], rax
0x18000645c  jmp     loc_18000635F
0x180006461  mov     eax, [rbx+90h]
0x180006467  add     rax, rdx
0x18000646a  mov     [rbx+50h], rdx
0x18000646e  mov     [rbx+58h], rax
0x180006472  mov     eax, [rbx+94h]
0x180006478  add     rax, rdx
0x18000647b  mov     [rbx+60h], rax
0x18000647f  jmp     loc_18000637F
0x180006484  test    [rax+8], dil
0x180006488  jz      loc_18000634B
0x18000648e  test    r9, r9
0x180006491  jnz     short loc_1800064AA
0x180006493  mov     eax, 6
0x180006498  jmp     loc_1800063D8
0x18000649d  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x1800064a0  call    ?process0@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; process0(DIRECTCOLORCONVFRM *)
0x1800064a5  jmp     loc_1800063CE
0x1800064aa  test    r8, r8
0x1800064ad  jz      short loc_180006493
0x1800064af  jmp     loc_18000634B
0x1800064b4  mov     r9d, [rbx+84h]
0x1800064bb  add     r9, rcx
0x1800064be  jmp     loc_18000643D
```
