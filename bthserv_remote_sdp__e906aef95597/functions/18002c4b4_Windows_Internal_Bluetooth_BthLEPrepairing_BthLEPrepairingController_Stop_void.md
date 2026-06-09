# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(void)

- ea: `0x18002c4b4`
- end: `0x18002c65e`
- name: `?Stop@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ`
- size: `426`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000f8ac`
- `0x18002b240`

## callees

- `0x180012004`
- `0x180012384`
- `0x18002c4b4`
- `0x18002c664`
- `0x18002c9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c540`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c5be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c5be`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)
{
  char v2; // bl
  bool v3; // dl
  unsigned int v4; // esi
  char v5; // r14
  int v6; // r8d
  int v7; // ecx
  _BYTE *v8; // rcx
  bool v9; // dl
  unsigned int v10; // eax
  int v11; // edx
  bool v12; // cf

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v4 = 0;
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v7 = *((_DWORD *)this + 2);
  if ( v7 )
  {
    if ( (unsigned int)(v7 - 1) <= 1 )
    {
      *((_DWORD *)this + 2) = 0;
      v5 = 1;
    }
    goto LABEL_18;
  }
  v4 = -2147483634;
  v8 = WPP_GLOBAL_Control;
  v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_18:
    v8 = WPP_GLOBAL_Control;
  }
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v8 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    v10 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StopInternal(this);
    v8 = WPP_GLOBAL_Control;
    v4 = v10;
  }
  v11 = 0;
  if ( v4 )
    v12 = v8[25] < 2u;
  else
    v12 = v8[25] < 5u;
  if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v11) = !v12, !v11) )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = v2;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v8 + 2), v11, v6, *((_QWORD *)v8 + 5));
  }
  return v4;
}

```

## disassembly

```asm
0x18002c4b4  mov     [rsp+arg_0], rbx
0x18002c4b9  mov     [rsp+arg_8], rbp
0x18002c4be  mov     [rsp+arg_10], rsi
0x18002c4c3  push    rdi
0x18002c4c4  push    r12
0x18002c4c6  push    r13
0x18002c4c8  push    r14
0x18002c4ca  push    r15
0x18002c4cc  sub     rsp, 60h
0x18002c4d0  mov     rdi, rcx
0x18002c4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4da  lea     r15, WPP_GLOBAL_Control
0x18002c4e1  mov     bl, 1
0x18002c4e3  cmp     rcx, r15
0x18002c4e6  jz      short loc_18002C4F2
0x18002c4e8  cmp     byte ptr [rcx+19h], 5
0x18002c4ec  jb      short loc_18002C4F2
0x18002c4ee  mov     dl, bl
0x18002c4f0  jmp     short loc_18002C4F4
0x18002c4f2  xor     dl, dl
0x18002c4f4  lea     r12, WPP_RECORDER_INITIALIZED
0x18002c4fb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002c502  lea     r13, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002c509  setnz   r8b
0x18002c50d  test    dl, dl
0x18002c50f  jnz     short loc_18002C516
0x18002c511  test    r8b, r8b
0x18002c514  jz      short loc_18002C534
0x18002c516  mov     r9, [rcx+28h]
0x18002c51a  mov     rcx, [rcx+10h]
0x18002c51e  mov     [rsp+88h+var_40], rdi
0x18002c523  mov     [rsp+88h+var_50], r13
0x18002c528  mov     [rsp+88h+var_58], 0Eh
0x18002c52f  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c534  lea     rbp, [rdi+30h]
0x18002c538  xor     esi, esi
0x18002c53a  mov     rcx, rbp; lpCriticalSection
0x18002c53d  xor     r14b, r14b
0x18002c540  call    cs:__imp_EnterCriticalSection
0x18002c547  nop     dword ptr [rax+rax+00h]
0x18002c54c  mov     ecx, [rdi+8]
0x18002c54f  test    ecx, ecx
0x18002c551  jz      short loc_18002C565
0x18002c553  sub     ecx, 1
0x18002c556  jz      short loc_18002C55D
0x18002c558  cmp     ecx, 1
0x18002c55b  jnz     short loc_18002C5AF
0x18002c55d  and     [rdi+8], esi
0x18002c560  mov     r14b, bl
0x18002c563  jmp     short loc_18002C5AF
0x18002c565  mov     esi, 8000000Eh
0x18002c56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c571  cmp     rcx, r15
0x18002c574  jz      short loc_18002C580
0x18002c576  cmp     byte ptr [rcx+19h], 2
0x18002c57a  jb      short loc_18002C580
0x18002c57c  mov     dl, bl
0x18002c57e  jmp     short loc_18002C582
0x18002c580  xor     dl, dl
0x18002c582  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002c589  setnz   r8b
0x18002c58d  test    dl, dl
0x18002c58f  jnz     short loc_18002C596
0x18002c591  test    r8b, r8b
0x18002c594  jz      short loc_18002C5B6
0x18002c596  mov     r9, [rcx+28h]
0x18002c59a  mov     rcx, [rcx+10h]
0x18002c59e  mov     [rsp+88h+var_50], r13
0x18002c5a3  mov     [rsp+88h+var_58], 0Fh
0x18002c5aa  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002c5af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5b6  test    rbp, rbp
0x18002c5b9  jz      short loc_18002C5D1
0x18002c5bb  mov     rcx, rbp; lpCriticalSection
0x18002c5be  call    cs:__imp_LeaveCriticalSection
0x18002c5c5  nop     dword ptr [rax+rax+00h]
0x18002c5ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5d1  test    r14b, r14b
0x18002c5d4  jz      short loc_18002C5E7
0x18002c5d6  mov     rcx, rdi; this
0x18002c5d9  call    ?StopInternal@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StopInternal(void)
0x18002c5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5e5  mov     esi, eax
0x18002c5e7  xor     edx, edx
0x18002c5e9  test    esi, esi
0x18002c5eb  jnz     short loc_18002C5F3
0x18002c5ed  cmp     byte ptr [rcx+19h], 5
0x18002c5f1  jmp     short loc_18002C5F7
0x18002c5f3  cmp     byte ptr [rcx+19h], 2
0x18002c5f7  setnb   dl
0x18002c5fa  cmp     rcx, r15
0x18002c5fd  jz      short loc_18002C603
0x18002c5ff  test    edx, edx
0x18002c601  jnz     short loc_18002C605
0x18002c603  xor     bl, bl
0x18002c605  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002c60c  setnz   r8b
0x18002c610  test    bl, bl
0x18002c612  jnz     short loc_18002C619
0x18002c614  test    r8b, r8b
0x18002c617  jz      short loc_18002C63D
0x18002c619  mov     r9, [rcx+28h]
0x18002c61d  mov     dl, bl
0x18002c61f  mov     rcx, [rcx+10h]
0x18002c623  mov     [rsp+88h+var_38], esi
0x18002c627  mov     [rsp+88h+var_40], rdi
0x18002c62c  mov     [rsp+88h+var_50], r13
0x18002c631  mov     [rsp+88h+var_58], 10h
0x18002c638  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002c63d  lea     r11, [rsp+88h+var_28]
0x18002c642  mov     eax, esi
0x18002c644  mov     rbx, [r11+30h]
0x18002c648  mov     rbp, [r11+38h]
0x18002c64c  mov     rsi, [r11+40h]
0x18002c650  mov     rsp, r11
0x18002c653  pop     r15
0x18002c655  pop     r14
0x18002c657  pop     r13
0x18002c659  pop     r12
0x18002c65b  pop     rdi
0x18002c65c  retn
```
