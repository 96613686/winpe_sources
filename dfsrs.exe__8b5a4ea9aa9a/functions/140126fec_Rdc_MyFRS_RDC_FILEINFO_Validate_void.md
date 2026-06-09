# Rdc::MyFRS_RDC_FILEINFO::Validate(void)

- ea: `0x140126fec`
- end: `0x14012718b`
- name: `?Validate@MyFRS_RDC_FILEINFO@Rdc@@QEAAPEAVFrsStatus@@XZ`
- size: `415`
- prototype: `struct FrsStatus *__fastcall(Rdc::MyFRS_RDC_FILEINFO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1401a9010`

## callees

- `0x140126fec`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140126ffd`
- `KERNEL32!GetCurrentThreadId` at `0x140127052`
- `KERNEL32!GetCurrentThreadId` at `0x14012707d`
- `KERNEL32!GetCurrentThreadId` at `0x1401270ab`
- `KERNEL32!GetCurrentThreadId` at `0x14012711a`
- `KERNEL32!GetCurrentThreadId` at `0x14012713d`
- `KERNEL32!GetCurrentThreadId` at `0x140127160`
- `KERNEL32!GetCurrentThreadId` at `0x140126ffd`
- `KERNEL32!GetCurrentThreadId` at `0x140127052`
- `KERNEL32!GetCurrentThreadId` at `0x14012707d`
- `KERNEL32!GetCurrentThreadId` at `0x1401270ab`
- `KERNEL32!GetCurrentThreadId` at `0x14012711a`
- `KERNEL32!GetCurrentThreadId` at `0x14012713d`
- `KERNEL32!GetCurrentThreadId` at `0x140127160`

## pseudocode

```c
struct FrsStatus *__fastcall Rdc::MyFRS_RDC_FILEINFO::Validate(Rdc::MyFRS_RDC_FILEINFO *this)
{
  DWORD CurrentThreadId; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  DWORD v5; // eax
  __int64 v6; // rcx
  unsigned int i; // edx
  __int64 v8; // r8
  int v9; // [rsp+30h] [rbp-28h]
  DWORD v10; // [rsp+38h] [rbp-20h]

  if ( *((_WORD *)this + 9) > 1u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v3 = 9041;
    v10 = CurrentThreadId;
    v9 = 643;
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v2,
                                 v3,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                 "Rdc::MyFRS_RDC_FILEINFO::Validate",
                                 v9,
                                 v10,
                                 0);
  }
  if ( !*((_WORD *)this + 8) )
  {
    v5 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v6,
                                 9042,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                 "Rdc::MyFRS_RDC_FILEINFO::Validate",
                                 648,
                                 v5,
                                 0);
  }
  if ( *((_BYTE *)this + 20) > 8u )
  {
    v10 = GetCurrentThreadId();
    v9 = 651;
LABEL_9:
    v3 = 9044;
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v2,
                                 v3,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                 "Rdc::MyFRS_RDC_FILEINFO::Validate",
                                 v9,
                                 v10,
                                 0);
  }
  if ( *((_DWORD *)this + 6) )
  {
    v10 = GetCurrentThreadId();
    v9 = 655;
    goto LABEL_9;
  }
  for ( i = 0; i < *((unsigned __int8 *)this + 20); ++i )
  {
    v8 = 68LL * i;
    if ( *(_WORD *)((char *)this + v8 + 28) != 1 )
    {
      v10 = GetCurrentThreadId();
      v9 = 659;
      goto LABEL_9;
    }
    if ( (unsigned __int16)(*(_WORD *)((char *)this + v8 + 30) - 128) > 0x3F80u )
    {
      v10 = GetCurrentThreadId();
      v9 = 664;
      goto LABEL_9;
    }
    if ( (unsigned __int16)(*(_WORD *)((char *)this + v8 + 32) - 2) > 0x5Eu )
    {
      v10 = GetCurrentThreadId();
      v9 = 668;
      goto LABEL_9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140126fec  sub     rsp, 58h
0x140126ff0  mov     r11d, 1
0x140126ff6  cmp     [rcx+12h], r11w
0x140126ffb  jbe     short loc_14012704B
0x140126ffd  call    cs:__imp_GetCurrentThreadId
0x140127004  nop     dword ptr [rax+rax+00h]
0x140127009  and     [rsp+58h+var_18], 0
0x14012700f  mov     edx, 2351h
0x140127014  mov     [rsp+58h+var_20], eax
0x140127018  mov     [rsp+58h+var_28], 283h
0x140127020  lea     rax, aRdcMyfrsRdcFil; "Rdc::MyFRS_RDC_FILEINFO::Validate"
0x140127027  mov     r9d, 3
0x14012702d  mov     [rsp+58h+var_30], rax
0x140127032  xor     r8d, r8d
0x140127035  lea     rax, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x14012703c  mov     [rsp+58h+var_38], rax
0x140127041  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140127046  jmp     loc_140127185
0x14012704b  cmp     [rcx+10h], r11w
0x140127050  jnb     short loc_140127077
0x140127052  call    cs:__imp_GetCurrentThreadId
0x140127059  nop     dword ptr [rax+rax+00h]
0x14012705e  and     [rsp+58h+var_18], 0
0x140127064  mov     edx, 2352h
0x140127069  mov     [rsp+58h+var_20], eax
0x14012706d  mov     [rsp+58h+var_28], 288h
0x140127075  jmp     short loc_140127020
0x140127077  cmp     byte ptr [rcx+14h], 8
0x14012707b  jbe     short loc_1401270A5
0x14012707d  call    cs:__imp_GetCurrentThreadId
0x140127084  nop     dword ptr [rax+rax+00h]
0x140127089  and     [rsp+58h+var_18], 0
0x14012708f  mov     [rsp+58h+var_20], eax
0x140127093  mov     [rsp+58h+var_28], 28Bh
0x14012709b  mov     edx, 2354h
0x1401270a0  jmp     loc_140127020
0x1401270a5  cmp     dword ptr [rcx+18h], 0
0x1401270a9  jz      short loc_1401270CB
0x1401270ab  call    cs:__imp_GetCurrentThreadId
0x1401270b2  nop     dword ptr [rax+rax+00h]
0x1401270b7  and     [rsp+58h+var_18], 0
0x1401270bd  mov     [rsp+58h+var_20], eax
0x1401270c1  mov     [rsp+58h+var_28], 28Fh
0x1401270c9  jmp     short loc_14012709B
0x1401270cb  movzx   r9d, byte ptr [rcx+14h]
0x1401270d0  xor     edx, edx
0x1401270d2  cmp     edx, r9d
0x1401270d5  jnb     loc_140127183
0x1401270db  mov     eax, edx
0x1401270dd  imul    r8, rax, 44h ; 'D'
0x1401270e1  cmp     [r8+rcx+1Ch], r11w
0x1401270e7  jnz     short loc_140127160
0x1401270e9  movzx   eax, word ptr [r8+rcx+1Eh]
0x1401270ef  mov     r10d, 80h
0x1401270f5  sub     ax, r10w
0x1401270f9  mov     r10d, 3F80h
0x1401270ff  cmp     ax, r10w
0x140127103  ja      short loc_14012713D
0x140127105  movzx   eax, word ptr [r8+rcx+20h]
0x14012710b  sub     ax, 2
0x14012710f  cmp     ax, 5Eh ; '^'
0x140127113  ja      short loc_14012711A
0x140127115  add     edx, r11d
0x140127118  jmp     short loc_1401270D2
0x14012711a  call    cs:__imp_GetCurrentThreadId
0x140127121  nop     dword ptr [rax+rax+00h]
0x140127126  and     [rsp+58h+var_18], 0
0x14012712c  mov     [rsp+58h+var_20], eax
0x140127130  mov     [rsp+58h+var_28], 29Ch
0x140127138  jmp     loc_14012709B
0x14012713d  call    cs:__imp_GetCurrentThreadId
0x140127144  nop     dword ptr [rax+rax+00h]
0x140127149  and     [rsp+58h+var_18], 0
0x14012714f  mov     [rsp+58h+var_20], eax
0x140127153  mov     [rsp+58h+var_28], 298h
0x14012715b  jmp     loc_14012709B
0x140127160  call    cs:__imp_GetCurrentThreadId
0x140127167  nop     dword ptr [rax+rax+00h]
0x14012716c  and     [rsp+58h+var_18], 0
0x140127172  mov     [rsp+58h+var_20], eax
0x140127176  mov     [rsp+58h+var_28], 293h
0x14012717e  jmp     loc_14012709B
0x140127183  xor     eax, eax
0x140127185  add     rsp, 58h
0x140127189  retn
```
