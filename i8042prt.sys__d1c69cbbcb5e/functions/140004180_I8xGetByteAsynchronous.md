# I8xGetByteAsynchronous

- ea: `0x140004180`
- end: `0x1400043d5`
- name: `I8xGetByteAsynchronous`
- size: `597`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140001d30`
- `0x140002610`

## callees

- `0x140004180`
- `0x1400043e0`
- `0x140004530`
- `0x140007b10`
- `0x14000daa0`

## pseudocode

```c
__int64 __fastcall I8xGetByteAsynchronous(char a1, unsigned __int8 *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebp
  char v6; // si
  unsigned __int8 v7; // al
  __int64 result; // rax
  unsigned __int16 v9; // r9
  unsigned int v10; // r8d
  const char *v11; // rax
  unsigned __int8 v12; // al
  __int64 v13; // [rsp+28h] [rbp-40h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      (__int64)a2,
      0x13u,
      0xFu,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( a1 == 1 )
      {
        v11 = "keyboard";
      }
      else
      {
        v11 = "mouse";
        if ( a1 != 2 )
          v11 = "8042 controller";
      }
      WPP_RECORDER_SF_s(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        (__int64)a2,
        0x14u,
        0x10u,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        v11);
    }
  }
  v4 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v5 = 0;
  v6 = 33;
  if ( a1 != 2 )
    v6 = 1;
  if ( *(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) )
  {
    do
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(v4 + 216));
      if ( (v7 & (unsigned __int8)v6) == v6 )
        break;
      if ( (v7 & 1) != 0 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL));
        *a2 = v12;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v13) = v12;
          WPP_RECORDER_SF_D(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            0x14u,
            0x11u,
            (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
            v13);
        }
      }
      else
      {
        ++v5;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            (__int64)a2,
            0x12u,
            0x12u,
            (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      }
      v4 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
    }
    while ( v5 < *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL) );
  }
  result = *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 72LL);
  if ( v5 >= (unsigned int)result )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return result;
    v9 = 19;
    v10 = 21;
    return WPP_RECORDER_SF_(
             (__int64)WPP_GLOBAL_Control->DeviceExtension,
             (__int64)a2,
             v10,
             v9,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  result = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL));
  *a2 = result;
  if ( a1 != 2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return result;
    v9 = 21;
    v10 = 19;
    return WPP_RECORDER_SF_(
             (__int64)WPP_GLOBAL_Control->DeviceExtension,
             (__int64)a2,
             v10,
             v9,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v13) = (unsigned __int8)result;
    return WPP_RECORDER_SF_D(
             (__int64)WPP_GLOBAL_Control->DeviceExtension,
             (_DWORD)a2,
             0x13u,
             0x14u,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
             v13);
  }
  return result;
}

```

## disassembly

```asm
0x140004180  push    rbx
0x140004182  push    rbp
0x140004183  push    rsi
0x140004184  push    rdi
0x140004185  push    r14
0x140004187  push    r15
0x140004189  sub     rsp, 38h
0x14000418d  mov     rdi, rdx
0x140004190  movzx   ebx, cl
0x140004193  lea     r14, WPP_RECORDER_INITIALIZED
0x14000419a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400041a1  lea     r15, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x1400041a8  jnz     loc_1400042C2
0x1400041ae  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400041b5  xor     ebp, ebp
0x1400041b7  cmp     bl, 2
0x1400041ba  mov     eax, 1
0x1400041bf  mov     esi, 21h ; '!'
0x1400041c4  cmovnz  esi, eax
0x1400041c7  xor     eax, eax
0x1400041c9  cmp     ax, [rcx+48h]
0x1400041cd  jnb     short loc_1400041ED
0x1400041cf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400041d6  mov     rcx, [rcx+0D8h]
0x1400041dd  call    _guard_dispatch_icall
0x1400041e2  movzx   ecx, sil
0x1400041e6  and     cl, al
0x1400041e8  cmp     cl, sil
0x1400041eb  jnz     short loc_14000425D
0x1400041ed  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400041f4  movzx   eax, word ptr [rcx+48h]
0x1400041f8  cmp     ebp, eax
0x1400041fa  jnb     loc_1400043B7
0x140004200  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140004207  mov     rcx, [rcx+0D0h]
0x14000420e  call    _guard_dispatch_icall
0x140004213  mov     [rdi], al
0x140004215  cmp     bl, 2
0x140004218  jnz     short loc_140004231
0x14000421a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140004221  jnz     short loc_14000428C
0x140004223  add     rsp, 38h
0x140004227  pop     r15
0x140004229  pop     r14
0x14000422b  pop     rdi
0x14000422c  pop     rsi
0x14000422d  pop     rbp
0x14000422e  pop     rbx
0x14000422f  retn
0x140004231  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140004238  jz      short loc_140004223
0x14000423a  mov     r9d, 15h
0x140004240  mov     r8d, 13h
0x140004246  mov     rcx, cs:WPP_GLOBAL_Control
0x14000424d  mov     [rsp+68h+var_48], r15
0x140004252  mov     rcx, [rcx+40h]
0x140004256  call    WPP_RECORDER_SF_
0x14000425b  jmp     short loc_140004223
0x14000425d  test    al, 1
0x14000425f  jnz     loc_14000433E
0x140004265  inc     ebp
0x140004267  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000426e  jnz     loc_140004394
0x140004274  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000427b  movzx   eax, word ptr [rcx+48h]
0x14000427f  cmp     ebp, eax
0x140004281  jb      loc_1400041CF
0x140004287  jmp     loc_1400041ED
0x14000428c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004293  mov     r9d, 14h
0x140004299  movzx   eax, al
0x14000429c  mov     r8d, 13h
0x1400042a2  mov     dword ptr [rsp+68h+var_40], eax
0x1400042a6  mov     [rsp+68h+var_48], r15
0x1400042ab  mov     rcx, [rcx+40h]
0x1400042af  call    WPP_RECORDER_SF_D
0x1400042b4  add     rsp, 38h
0x1400042b8  pop     r15
0x1400042ba  pop     r14
0x1400042bc  pop     rdi
0x1400042bd  pop     rsi
0x1400042be  pop     rbp
0x1400042bf  pop     rbx
0x1400042c0  retn
0x1400042c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042c9  mov     r9d, 0Fh
0x1400042cf  mov     r8d, 13h
0x1400042d5  mov     [rsp+68h+var_48], r15
0x1400042da  mov     rcx, [rcx+40h]
0x1400042de  call    WPP_RECORDER_SF_
0x1400042e3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400042ea  jz      loc_1400041AE
0x1400042f0  cmp     bl, 1
0x1400042f3  jz      short loc_140004335
0x1400042f5  cmp     bl, 2
0x1400042f8  lea     rax, aMouse_0; "mouse"
0x1400042ff  lea     rcx, a8042Controller; "8042 controller"
0x140004306  cmovnz  rax, rcx
0x14000430a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004311  mov     r9d, 10h
0x140004317  mov     [rsp+68h+var_40], rax
0x14000431c  mov     r8d, 14h
0x140004322  mov     [rsp+68h+var_48], r15
0x140004327  mov     rcx, [rcx+40h]
0x14000432b  call    WPP_RECORDER_SF_s
0x140004330  jmp     loc_1400041AE
0x140004335  lea     rax, aKeyboard; "keyboard"
0x14000433c  jmp     short loc_14000430A
0x14000433e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140004345  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000434c  mov     rcx, [rcx+0D0h]
0x140004353  call    _guard_dispatch_icall
0x140004358  mov     [rdi], al
0x14000435a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140004361  jz      loc_140004274
0x140004367  mov     rcx, cs:WPP_GLOBAL_Control
0x14000436e  mov     r9d, 11h
0x140004374  movzx   eax, al
0x140004377  mov     r8d, 14h
0x14000437d  mov     dword ptr [rsp+68h+var_40], eax
0x140004381  mov     [rsp+68h+var_48], r15
0x140004386  mov     rcx, [rcx+40h]
0x14000438a  call    WPP_RECORDER_SF_D
0x14000438f  jmp     loc_140004274
0x140004394  mov     rcx, cs:WPP_GLOBAL_Control
0x14000439b  mov     r9d, 12h
0x1400043a1  mov     r8d, r9d
0x1400043a4  mov     [rsp+68h+var_48], r15
0x1400043a9  mov     rcx, [rcx+40h]
0x1400043ad  call    WPP_RECORDER_SF_
0x1400043b2  jmp     loc_140004274
0x1400043b7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400043be  jz      loc_140004223
0x1400043c4  mov     r9d, 13h
0x1400043ca  mov     r8d, 15h
0x1400043d0  jmp     loc_140004246
```
