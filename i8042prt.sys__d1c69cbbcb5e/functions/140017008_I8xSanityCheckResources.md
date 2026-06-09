# I8xSanityCheckResources

- ea: `0x140017008`
- end: `0x1400171e2`
- name: `I8xSanityCheckResources`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400171e8`
- `0x14001e950`

## callees

- `0x140004530`
- `0x140009e28`
- `0x140017008`

## import_xrefs

- `ntoskrnl!MmMapIoSpaceEx` at `0x1400170ea`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400170ea`

## pseudocode

```c
char I8xSanityCheckResources()
{
  _DWORD *v0; // rdi
  int v1; // eax
  __int128 *v2; // rdx
  __int128 *v3; // r8
  int v4; // eax
  int v5; // ecx
  __int128 v6; // xmm0
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 i; // rsi
  void *v11; // rax
  __int64 j; // r9
  __int64 k; // rbx
  int v14; // r8d
  const char *v15; // rcx
  int v17; // [rsp+20h] [rbp-58h]

  v0 = *(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v1 = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 64LL);
  if ( v1 )
  {
    v2 = (__int128 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 24LL);
    v3 = (__int128 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 44LL);
    if ( v1 == 1 )
    {
      *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 36LL) = 1;
      v4 = v0[10];
      *v3 = *v2;
      v0[15] = v4;
      v0[12] += 4;
      v0[16] = 2;
    }
    if ( v0[12] < v0[7] )
    {
      v5 = v0[10];
      v6 = *v3;
      v7 = v0[15];
      *v3 = *v2;
      v0[15] = v5;
      *v2 = v6;
      v0[10] = v7;
    }
    v8 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
    if ( !*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL) )
    {
      if ( BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            (__int64)v2,
            0x10u,
            0x61u,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        v9 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
        for ( i = 0;
              (unsigned int)i < *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 64LL);
              v9 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
        {
          *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8 * i + 208) = MmMapIoSpaceEx(
                                                                                            *(_QWORD *)(v9 + 20 * i + 28),
                                                                                            *(unsigned int *)(v9 + 20 * i + 36),
                                                                                            516);
          i = (unsigned int)(i + 1);
        }
        *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = I8xReadRegisterUchar;
        v11 = I8xWriteRegisterUchar;
      }
      else
      {
        for ( j = 0;
              (unsigned int)j < *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 64LL);
              v8 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
        {
          *(_QWORD *)(v8 + 8 * j + 208) = *(unsigned int *)(v8 + 20 * j + 28);
          j = (unsigned int)(j + 1);
        }
        *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = I8xReadPortUchar;
        v11 = I8xWritePortUchar;
      }
      WPP_MAIN_CB.Queue.Wcb.DeviceObject = v11;
    }
    for ( k = 0; (unsigned int)k < v0[16]; k = (unsigned int)(k + 1) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = v0[5 * k + 7];
        v15 = "Sharable";
        if ( BYTE1(v0[5 * k + 6]) != 3 )
          v15 = "NonSharable";
        WPP_RECORDER_SF_sdDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v0[5 * k + 9] + v14 - 1,
          v14,
          (unsigned int)"NonSharable",
          v17,
          (__int64)v15,
          k,
          v14,
          LOBYTE(v0[5 * k + 9]) + v14 - 1);
      }
    }
    LOBYTE(v1) = 1;
  }
  return v1;
}

```

## disassembly

```asm
0x140017008  push    rbx
0x14001700a  push    rsi
0x14001700b  push    rdi
0x14001700c  push    r15
0x14001700e  sub     rsp, 58h
0x140017012  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140017019  mov     eax, [rdi+40h]
0x14001701c  test    eax, eax
0x14001701e  jz      loc_1400171D7
0x140017024  lea     rdx, [rdi+18h]
0x140017028  lea     r8, [rdi+2Ch]
0x14001702c  cmp     eax, 1
0x14001702f  jnz     short loc_14001704D
0x140017031  mov     [rdi+24h], eax
0x140017034  movups  xmm0, xmmword ptr [rdx]
0x140017037  mov     eax, [rdx+10h]
0x14001703a  movups  xmmword ptr [r8], xmm0
0x14001703e  mov     [r8+10h], eax
0x140017042  add     dword ptr [rdi+30h], 4
0x140017046  mov     dword ptr [rdi+40h], 2
0x14001704d  mov     eax, [rdi+1Ch]
0x140017050  cmp     [rdi+30h], eax
0x140017053  jnb     short loc_140017071
0x140017055  movups  xmm1, xmmword ptr [rdx]
0x140017058  mov     ecx, [rdx+10h]
0x14001705b  movups  xmm0, xmmword ptr [r8]
0x14001705f  mov     eax, [r8+10h]
0x140017063  movups  xmmword ptr [r8], xmm1
0x140017067  mov     [r8+10h], ecx
0x14001706b  movups  xmmword ptr [rdx], xmm0
0x14001706e  mov     [rdx+10h], eax
0x140017071  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140017078  lea     r15, WPP_RECORDER_INITIALIZED
0x14001707f  cmp     qword ptr [r8+0D0h], 0
0x140017087  jnz     loc_140017173
0x14001708d  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 0
0x140017094  jz      loc_14001712D
0x14001709a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400170a1  jz      short loc_1400170C9
0x1400170a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170aa  lea     rax, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x1400170b1  mov     r9d, 61h ; 'a'
0x1400170b7  mov     [rsp+78h+var_58], rax
0x1400170bc  mov     rcx, [rcx+40h]
0x1400170c0  lea     r8d, [r9-51h]
0x1400170c4  call    WPP_RECORDER_SF_
0x1400170c9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400170d0  xor     esi, esi
0x1400170d2  cmp     [rax+40h], esi
0x1400170d5  jbe     short loc_140017116
0x1400170d7  lea     rcx, [rsi+rsi*4]
0x1400170db  mov     r8d, 204h
0x1400170e1  mov     edx, [rax+rcx*4+24h]
0x1400170e5  mov     rcx, [rax+rcx*4+1Ch]
0x1400170ea  call    cs:__imp_MmMapIoSpaceEx
0x1400170f1  nop     dword ptr [rax+rax+00h]
0x1400170f6  mov     rcx, rax
0x1400170f9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140017100  mov     [rax+rsi*8+0D0h], rcx
0x140017108  inc     esi
0x14001710a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140017111  cmp     esi, [rax+40h]
0x140017114  jb      short loc_1400170D7
0x140017116  lea     rax, I8xReadRegisterUchar
0x14001711d  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x140017124  lea     rax, I8xWriteRegisterUchar
0x14001712b  jmp     short loc_14001716C
0x14001712d  xor     r9d, r9d
0x140017130  cmp     [r8+40h], r9d
0x140017134  jbe     short loc_140017157
0x140017136  lea     rax, [r9+r9*4]
0x14001713a  mov     ecx, [r8+rax*4+1Ch]
0x14001713f  mov     [r8+r9*8+0D0h], rcx
0x140017147  inc     r9d
0x14001714a  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140017151  cmp     r9d, [r8+40h]
0x140017155  jb      short loc_140017136
0x140017157  lea     rax, I8xReadPortUchar
0x14001715e  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x140017165  lea     rax, I8xWritePortUchar
0x14001716c  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rax
0x140017173  xor     ebx, ebx
0x140017175  cmp     [rdi+40h], ebx
0x140017178  jbe     short loc_1400171D5
0x14001717a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140017181  jz      short loc_1400171CE
0x140017183  lea     rcx, [rbx+rbx*4]
0x140017187  mov     r8d, [rdi+rcx*4+1Ch]
0x14001718c  lea     r9, aNonsharable; "NonSharable"
0x140017193  mov     al, [rdi+rcx*4+19h]
0x140017197  lea     edx, [r8-1]
0x14001719b  add     edx, [rdi+rcx*4+24h]
0x14001719f  lea     rcx, aSharable; "Sharable"
0x1400171a6  mov     [rsp+78h+var_38], edx
0x1400171aa  cmp     al, 3
0x1400171ac  mov     [rsp+78h+var_40], r8d
0x1400171b1  cmovnz  rcx, r9
0x1400171b5  mov     [rsp+78h+var_48], ebx
0x1400171b9  mov     [rsp+78h+var_50], rcx
0x1400171be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171c5  mov     rcx, [rcx+40h]
0x1400171c9  call    WPP_RECORDER_SF_sdDD
0x1400171ce  inc     ebx
0x1400171d0  cmp     ebx, [rdi+40h]
0x1400171d3  jb      short loc_14001717A
0x1400171d5  mov     al, 1
0x1400171d7  add     rsp, 58h
0x1400171db  pop     r15
0x1400171dd  pop     rdi
0x1400171de  pop     rsi
0x1400171df  pop     rbx
0x1400171e0  retn
```
