# I8xPutByteAsynchronous

- ea: `0x140001130`
- end: `0x1400012f5`
- name: `I8xPutByteAsynchronous`
- size: `453`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001100`
- `0x140001360`
- `0x140002610`
- `0x14000c3e0`
- `0x14000d880`

## callees

- `0x140001130`
- `0x140004530`
- `0x140007b10`
- `0x14000daa0`

## pseudocode

```c
__int64 __fastcall I8xPutByteAsynchronous(char a1, __int64 a2)
{
  int v2; // esi
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 result; // rax
  __int64 v7; // rcx
  unsigned __int16 v8; // r9
  unsigned int v9; // r8d

  v2 = (unsigned __int8)a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      0x13u,
      0x37u,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  v4 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v5 = 0;
  if ( *(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
  {
    while ( 1 )
    {
      ++v5;
      if ( ((*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(v4 + 216)) & 2) == 0 )
        break;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          a2,
          0x12u,
          0x38u,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      v4 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      if ( v5 >= *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
        goto LABEL_8;
    }
  }
  else
  {
LABEL_8:
    ++v5;
  }
  result = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  if ( v5 >= *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return result;
    v8 = 57;
    v9 = 21;
    return WPP_RECORDER_SF_(
             (__int64)WPP_GLOBAL_Control->DeviceExtension,
             a2,
             v9,
             v8,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  if ( a1 == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        a2,
        0x14u,
        0x3Au,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        v2);
    v7 = *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 216LL);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        a2,
        0x14u,
        0x3Bu,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        v2);
    v7 = *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL);
  }
  result = ((__int64 (__fastcall *)(__int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.DeviceObject)(v7, (unsigned __int8)v2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = 60;
    v9 = 19;
    return WPP_RECORDER_SF_(
             (__int64)WPP_GLOBAL_Control->DeviceExtension,
             a2,
             v9,
             v8,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140001130  push    rbx
0x140001132  push    rbp
0x140001133  push    rsi
0x140001134  push    rdi
0x140001135  push    r14
0x140001137  sub     rsp, 30h
0x14000113b  movzx   esi, dl
0x14000113e  movzx   edi, cl
0x140001141  lea     rbp, WPP_RECORDER_INITIALIZED
0x140001148  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000114f  lea     r14, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140001156  jnz     loc_140001249
0x14000115c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001163  xor     ebx, ebx
0x140001165  xor     eax, eax
0x140001167  cmp     ax, [rcx+48h]
0x14000116b  jnb     short loc_1400011A1
0x14000116d  nop     dword ptr [rax]
0x140001170  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140001177  inc     ebx
0x140001179  mov     rcx, [rcx+0D8h]
0x140001180  call    _guard_dispatch_icall
0x140001185  test    al, 2
0x140001187  jz      short loc_1400011A3
0x140001189  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140001190  jnz     short loc_140001200
0x140001192  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001199  movzx   eax, word ptr [rcx+48h]
0x14000119d  cmp     ebx, eax
0x14000119f  jb      short loc_140001170
0x1400011a1  inc     ebx
0x1400011a3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400011aa  movzx   ecx, word ptr [rax+48h]
0x1400011ae  cmp     ebx, ecx
0x1400011b0  jnb     loc_14000126F
0x1400011b6  cmp     dil, 1
0x1400011ba  jz      loc_14000128A
0x1400011c0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400011c7  jnz     loc_1400012CB
0x1400011cd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400011d4  mov     rcx, [rcx+0D0h]
0x1400011db  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400011e2  movzx   edx, sil
0x1400011e6  call    _guard_dispatch_icall
0x1400011eb  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400011f2  jnz     short loc_140001226
0x1400011f4  add     rsp, 30h
0x1400011f8  pop     r14
0x1400011fa  pop     rdi
0x1400011fb  pop     rsi
0x1400011fc  pop     rbp
0x1400011fd  pop     rbx
0x1400011fe  retn
0x140001200  mov     rcx, cs:WPP_GLOBAL_Control
0x140001207  mov     r9d, 38h ; '8'
0x14000120d  mov     r8d, 12h
0x140001213  mov     [rsp+58h+var_38], r14
0x140001218  mov     rcx, [rcx+40h]
0x14000121c  call    WPP_RECORDER_SF_
0x140001221  jmp     loc_140001192
0x140001226  mov     r9d, 3Ch ; '<'
0x14000122c  mov     r8d, 13h
0x140001232  mov     rcx, cs:WPP_GLOBAL_Control
0x140001239  mov     [rsp+58h+var_38], r14
0x14000123e  mov     rcx, [rcx+40h]
0x140001242  call    WPP_RECORDER_SF_
0x140001247  jmp     short loc_1400011F4
0x140001249  mov     rcx, cs:WPP_GLOBAL_Control
0x140001250  mov     r9d, 37h ; '7'
0x140001256  mov     r8d, 13h
0x14000125c  mov     [rsp+58h+var_38], r14
0x140001261  mov     rcx, [rcx+40h]
0x140001265  call    WPP_RECORDER_SF_
0x14000126a  jmp     loc_14000115C
0x14000126f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140001276  jz      loc_1400011F4
0x14000127c  mov     r9d, 39h ; '9'
0x140001282  mov     r8d, 15h
0x140001288  jmp     short loc_140001232
0x14000128a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140001291  jz      short loc_1400012B8
0x140001293  mov     rcx, cs:WPP_GLOBAL_Control
0x14000129a  mov     r9d, 3Ah ; ':'
0x1400012a0  mov     [rsp+58h+var_30], esi
0x1400012a4  mov     r8d, 14h
0x1400012aa  mov     [rsp+58h+var_38], r14
0x1400012af  mov     rcx, [rcx+40h]
0x1400012b3  call    WPP_RECORDER_SF_D
0x1400012b8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400012bf  mov     rcx, [rcx+0D8h]
0x1400012c6  jmp     loc_1400011DB
0x1400012cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012d2  mov     r9d, 3Bh ; ';'
0x1400012d8  mov     [rsp+58h+var_30], esi
0x1400012dc  mov     r8d, 14h
0x1400012e2  mov     [rsp+58h+var_38], r14
0x1400012e7  mov     rcx, [rcx+40h]
0x1400012eb  call    WPP_RECORDER_SF_D
0x1400012f0  jmp     loc_1400011CD
```
