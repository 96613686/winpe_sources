# I8xInitiateIo

- ea: `0x140001360`
- end: `0x1400014d3`
- name: `I8xInitiateIo`
- size: `371`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001300`
- `0x140001d30`
- `0x140002610`

## callees

- `0x140001130`
- `0x140001360`
- `0x140004530`
- `0x140006950`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x140001493`
- `ntoskrnl!KeInsertQueueDpc` at `0x140001493`

## pseudocode

```c
char __fastcall I8xInitiateIo(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  char result; // al
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // [rsp+28h] [rbp-40h]
  int v12; // [rsp+30h] [rbp-38h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3u,
      0x63u,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  v3 = *(_QWORD *)(a1 + 64);
  result = WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) = 3;
  v5 = *(_QWORD *)(v3 + 512);
  if ( v5 && *(_DWORD *)(v3 + 528) == 1 )
  {
    v6 = *(unsigned int *)(v3 + 520);
    if ( (unsigned int)v6 >= *(_DWORD *)(v3 + 524) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v6,
          5u,
          0x65u,
          (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
      v10 = -1073414130;
      if ( !*(_BYTE *)(v3 + 565) )
        v10 = -1073414092;
      result = KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)v10);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = *(unsigned __int8 *)(v6 + v5);
        v11 = *(_DWORD *)(v3 + 520);
        WPP_RECORDER_SF_dD(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v6,
          4u,
          0x64u,
          (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
          v11,
          v12);
      }
      if ( !*(_BYTE *)(v3 + 565) )
      {
        LOBYTE(v6) = -44;
        I8xPutByteAsynchronous(1, v6);
      }
      v7 = *(unsigned int *)(v3 + 520);
      v8 = *(unsigned __int8 *)(v7 + v5);
      *(_DWORD *)(v3 + 520) = v7 + 1;
      result = I8xPutByteAsynchronous(0, v8);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WPP_RECORDER_SF_(
               (__int64)WPP_GLOBAL_Control->DeviceExtension,
               v9,
               3u,
               0x66u,
               (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140001360  push    rbx
0x140001362  push    rbp
0x140001363  push    rsi
0x140001364  push    rdi
0x140001365  sub     rsp, 48h
0x140001369  mov     rbx, rcx
0x14000136c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001373  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000137a  lea     rbp, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140001381  jz      short loc_1400013A4
0x140001383  mov     rcx, cs:WPP_GLOBAL_Control
0x14000138a  mov     r9d, 63h ; 'c'
0x140001390  mov     r8d, 3
0x140001396  mov     [rsp+68h+var_48], rbp
0x14000139b  mov     rcx, [rcx+40h]
0x14000139f  call    WPP_RECORDER_SF_
0x1400013a4  mov     rbx, [rbx+40h]
0x1400013a8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400013af  mov     dword ptr [rax+0CCh], 3
0x1400013b9  mov     rdi, [rbx+200h]
0x1400013c0  test    rdi, rdi
0x1400013c3  jz      loc_1400014C9
0x1400013c9  cmp     dword ptr [rbx+210h], 1
0x1400013d0  jnz     loc_1400014C9
0x1400013d6  mov     edx, [rbx+208h]
0x1400013dc  cmp     edx, [rbx+20Ch]
0x1400013e2  jnb     short loc_140001447
0x1400013e4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400013eb  jz      short loc_14000141A
0x1400013ed  movzx   ecx, byte ptr [rdx+rdi]
0x1400013f1  mov     r9d, 64h ; 'd'
0x1400013f7  mov     [rsp+68h+var_38], ecx
0x1400013fb  mov     r8d, 4
0x140001401  mov     rcx, cs:WPP_GLOBAL_Control
0x140001408  mov     [rsp+68h+var_40], edx
0x14000140c  mov     [rsp+68h+var_48], rbp
0x140001411  mov     rcx, [rcx+40h]
0x140001415  call    WPP_RECORDER_SF_dD
0x14000141a  cmp     byte ptr [rbx+235h], 0
0x140001421  jnz     short loc_14000142C
0x140001423  mov     dl, 0D4h
0x140001425  mov     cl, 1
0x140001427  call    I8xPutByteAsynchronous
0x14000142c  mov     eax, [rbx+208h]
0x140001432  xor     ecx, ecx
0x140001434  movzx   edx, byte ptr [rax+rdi]
0x140001438  inc     eax
0x14000143a  mov     [rbx+208h], eax
0x140001440  call    I8xPutByteAsynchronous
0x140001445  jmp     short loc_14000149F
0x140001447  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000144e  jz      short loc_140001471
0x140001450  mov     rcx, cs:WPP_GLOBAL_Control
0x140001457  mov     r9d, 65h ; 'e'
0x14000145d  mov     r8d, 5
0x140001463  mov     [rsp+68h+var_48], rbp
0x140001468  mov     rcx, [rcx+40h]
0x14000146c  call    WPP_RECORDER_SF_
0x140001471  cmp     byte ptr [rbx+235h], 0
0x140001478  lea     rcx, [rbx+0E8h]; Dpc
0x14000147f  mov     rax, 0FFFFFFFFC0050034h
0x140001486  mov     r8, 0FFFFFFFFC005000Eh
0x14000148d  cmovz   r8, rax; SystemArgument2
0x140001491  xor     edx, edx; SystemArgument1
0x140001493  call    cs:__imp_KeInsertQueueDpc
0x14000149a  nop     dword ptr [rax+rax+00h]
0x14000149f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400014a6  jz      short loc_1400014C9
0x1400014a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400014af  mov     r9d, 66h ; 'f'
0x1400014b5  mov     r8d, 3
0x1400014bb  mov     [rsp+68h+var_48], rbp
0x1400014c0  mov     rcx, [rcx+40h]
0x1400014c4  call    WPP_RECORDER_SF_
0x1400014c9  add     rsp, 48h
0x1400014cd  pop     rdi
0x1400014ce  pop     rsi
0x1400014cf  pop     rbp
0x1400014d0  pop     rbx
0x1400014d1  retn
```
