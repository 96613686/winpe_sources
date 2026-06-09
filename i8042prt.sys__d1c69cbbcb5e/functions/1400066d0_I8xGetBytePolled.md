# I8xGetBytePolled

- ea: `0x1400066d0`
- end: `0x140006949`
- name: `I8xGetBytePolled`
- size: `633`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140005830`
- `0x1400059c0`
- `0x14000d8a0`
- `0x140019cfc`
- `0x14001a144`
- `0x14001a19c`
- `0x14001b574`
- `0x14001d8b0`

## callees

- `0x1400043e0`
- `0x140004530`
- `0x140005440`
- `0x1400066d0`
- `0x140007b10`
- `0x14000daa0`

## import_xrefs

- `HAL!KeStallExecutionProcessor` at `0x140006771`
- `HAL!KeStallExecutionProcessor` at `0x140006771`

## pseudocode

```c
__int64 __fastcall I8xGetBytePolled(char a1, unsigned __int8 *a2)
{
  const char *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  char v7; // di
  unsigned __int8 v8; // al
  __int64 v9; // rdx
  unsigned __int8 v10; // al
  int v11; // edx
  unsigned __int8 v13; // al
  __int64 v14; // [rsp+28h] [rbp-50h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      (__int64)a2,
      0x13u,
      0x16u,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  if ( a1 == 1 )
  {
    v4 = "keyboard";
  }
  else
  {
    v4 = "mouse";
    if ( a1 != 2 )
      v4 = "8042 controller";
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      20,
      23,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      (__int64)v4);
  v5 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v6 = 0;
  v7 = 33;
  if ( a1 != 2 )
    v7 = 1;
  if ( !*(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
    goto LABEL_18;
  do
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(v5 + 216));
    if ( (v8 & (unsigned __int8)v7) == v7 )
      break;
    if ( (v8 & 1) != 0 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL));
      *a2 = v13;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v14) = v13;
        WPP_RECORDER_SF_D(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v9,
          0x14u,
          0x18u,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v14);
      }
    }
    else
    {
      KeStallExecutionProcessor(*(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 78LL));
      ++v6;
    }
    v5 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  }
  while ( v6 < *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) );
  if ( !v6 )
    goto LABEL_18;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      18,
      25,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      *(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 78LL),
      v6);
  if ( v6 >= *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v9,
        0x15u,
        0x1Au,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    return 3221225653LL;
  }
  else
  {
LABEL_18:
    v10 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL));
    *a2 = v10;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v14) = v10;
      WPP_RECORDER_SF_D(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v11,
        0x13u,
        0x1Bu,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        v14);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400066d0  push    rbx
0x1400066d2  push    rbp
0x1400066d3  push    rsi
0x1400066d4  push    rdi
0x1400066d5  push    r14
0x1400066d7  push    r15
0x1400066d9  sub     rsp, 48h
0x1400066dd  mov     r14, rdx
0x1400066e0  movzx   esi, cl
0x1400066e3  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400066ea  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400066f1  lea     r15, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x1400066f8  jnz     loc_1400067EC
0x1400066fe  cmp     sil, 1
0x140006702  jnz     loc_140006876
0x140006708  lea     rax, aKeyboard; "keyboard"
0x14000670f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006716  jnz     loc_140006812
0x14000671c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006723  xor     ebx, ebx
0x140006725  cmp     sil, 2
0x140006729  mov     eax, 1
0x14000672e  mov     edi, 21h ; '!'
0x140006733  cmovnz  edi, eax
0x140006736  xor     eax, eax
0x140006738  cmp     ax, [rcx+48h]
0x14000673c  jnb     short loc_1400067B2
0x14000673e  xchg    ax, ax
0x140006740  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140006747  mov     rcx, [rcx+0D8h]
0x14000674e  call    _guard_dispatch_icall
0x140006753  movzx   ecx, dil
0x140006757  and     cl, al
0x140006759  cmp     cl, dil
0x14000675c  jz      short loc_14000678E
0x14000675e  test    al, 1
0x140006760  jnz     loc_140006891
0x140006766  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000676d  movzx   ecx, word ptr [rax+4Eh]; MicroSeconds
0x140006771  call    cs:__imp_KeStallExecutionProcessor
0x140006778  nop     dword ptr [rax+rax+00h]
0x14000677d  inc     ebx
0x14000677f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006786  movzx   eax, word ptr [rcx+48h]
0x14000678a  cmp     ebx, eax
0x14000678c  jb      short loc_140006740
0x14000678e  test    ebx, ebx
0x140006790  jz      short loc_1400067B2
0x140006792  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006799  jnz     loc_14000683D
0x14000679f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400067a6  movzx   ecx, word ptr [rax+48h]
0x1400067aa  cmp     ebx, ecx
0x1400067ac  jnb     loc_1400068E8
0x1400067b2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400067b9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400067c0  mov     rcx, [rcx+0D0h]
0x1400067c7  call    _guard_dispatch_icall
0x1400067cc  mov     [r14], al
0x1400067cf  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400067d6  jnz     loc_14000691C
0x1400067dc  xor     eax, eax
0x1400067de  add     rsp, 48h
0x1400067e2  pop     r15
0x1400067e4  pop     r14
0x1400067e6  pop     rdi
0x1400067e7  pop     rsi
0x1400067e8  pop     rbp
0x1400067e9  pop     rbx
0x1400067ea  retn
0x1400067ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067f3  mov     r9d, 16h
0x1400067f9  mov     r8d, 13h
0x1400067ff  mov     [rsp+78h+var_58], r15
0x140006804  mov     rcx, [rcx+40h]
0x140006808  call    WPP_RECORDER_SF_
0x14000680d  jmp     loc_1400066FE
0x140006812  mov     rcx, cs:WPP_GLOBAL_Control
0x140006819  mov     r9d, 17h
0x14000681f  mov     [rsp+78h+var_50], rax
0x140006824  mov     r8d, 14h
0x14000682a  mov     [rsp+78h+var_58], r15
0x14000682f  mov     rcx, [rcx+40h]
0x140006833  call    WPP_RECORDER_SF_s
0x140006838  jmp     loc_14000671C
0x14000683d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006844  mov     r9d, 19h
0x14000684a  mov     [rsp+78h+var_48], ebx
0x14000684e  mov     r8d, 12h
0x140006854  movzx   ecx, word ptr [rax+4Eh]
0x140006858  mov     dword ptr [rsp+78h+var_50], ecx
0x14000685c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006863  mov     [rsp+78h+var_58], r15
0x140006868  mov     rcx, [rcx+40h]
0x14000686c  call    WPP_RECORDER_SF_dd
0x140006871  jmp     loc_14000679F
0x140006876  cmp     sil, 2
0x14000687a  lea     rax, aMouse_0; "mouse"
0x140006881  lea     rcx, a8042Controller; "8042 controller"
0x140006888  cmovnz  rax, rcx
0x14000688c  jmp     loc_14000670F
0x140006891  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006898  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000689f  mov     rcx, [rcx+0D0h]
0x1400068a6  call    _guard_dispatch_icall
0x1400068ab  mov     [r14], al
0x1400068ae  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400068b5  jz      loc_14000677F
0x1400068bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068c2  mov     r9d, 18h
0x1400068c8  movzx   eax, al
0x1400068cb  mov     r8d, 14h
0x1400068d1  mov     dword ptr [rsp+78h+var_50], eax
0x1400068d5  mov     [rsp+78h+var_58], r15
0x1400068da  mov     rcx, [rcx+40h]
0x1400068de  call    WPP_RECORDER_SF_D
0x1400068e3  jmp     loc_14000677F
0x1400068e8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400068ef  jz      short loc_140006912
0x1400068f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068f8  mov     r9d, 1Ah
0x1400068fe  mov     r8d, 15h
0x140006904  mov     [rsp+78h+var_58], r15
0x140006909  mov     rcx, [rcx+40h]
0x14000690d  call    WPP_RECORDER_SF_
0x140006912  mov     eax, 0C00000B5h
0x140006917  jmp     loc_1400067DE
0x14000691c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006923  mov     r9d, 1Bh
0x140006929  movzx   eax, al
0x14000692c  mov     r8d, 13h
0x140006932  mov     dword ptr [rsp+78h+var_50], eax
0x140006936  mov     [rsp+78h+var_58], r15
0x14000693b  mov     rcx, [rcx+40h]
0x14000693f  call    WPP_RECORDER_SF_D
0x140006944  jmp     loc_1400067DC
```
