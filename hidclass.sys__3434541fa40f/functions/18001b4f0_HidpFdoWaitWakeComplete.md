# HidpFdoWaitWakeComplete

- ea: `0x18001b4f0`
- end: `0x18001b6fb`
- name: `HidpFdoWaitWakeComplete`
- size: `523`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014b0c`

## callees

- `0x18000a15c`
- `0x180010814`
- `0x180013a14`
- `0x18001b4f0`
- `0x18001b744`
- `0x18002497c`
- `0x180027ba0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18001b60d`
- `ntoskrnl!MmBadPointer` at `0x18001b6b0`

## pseudocode

```c
void __fastcall HidpFdoWaitWakeComplete(
        PDEVICE_OBJECT DeviceObject,
        __int64 MinorFunction,
        __int64 PowerState,
        __int64 Context,
        PIO_STATUS_BLOCK IoStatus)
{
  int v6; // edx
  int v7; // r8d
  int v8; // r8d
  signed __int32 v9; // eax
  _WORD *v10; // r9
  unsigned int v11; // r11d
  unsigned __int16 v12; // r10
  __int64 v13; // rdx
  _WORD v14[16]; // [rsp+60h] [rbp-78h] BYREF
  _WORD v15[16]; // [rsp+80h] [rbp-58h] BYREF

  if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(
                       DeviceObject,
                       MinorFunction,
                       PowerState,
                       Context) )
  {
    if ( !IoStatus )
      goto LABEL_21;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v6) = 0;
    }
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        *(_QWORD *)(Context + 672),
        4,
        9,
        43,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *(_QWORD *)Context,
        *(_QWORD *)(Context + 368),
        IoStatus->Status);
    }
  }
  else if ( !IoStatus )
  {
    goto LABEL_21;
  }
  if ( IoStatus->Status >= 0 )
  {
    if ( *(_DWORD *)(Context + 1776) )
    {
      v8 = MEMORY[0xFFFFF78000000014];
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)(Context + 1816), 0, 0);
      v10 = *(_WORD **)(Context + 152);
      if ( v10 )
      {
        if ( v10 != MmBadPointer )
        {
          v11 = *(_DWORD *)(Context + 168);
          v12 = 0;
          if ( v11 )
          {
            do
            {
              if ( v12 >= 0x10u )
                break;
              v13 = v12++;
              v15[v13] = v10[212 * v13 + 5];
              v14[v13] = v10[212 * v13 + 4];
            }
            while ( v12 < v11 );
            if ( v12 )
              TraceLoggingWaitWakeCompletedInSuppressInput(
                Context,
                _InterlockedCompareExchange((volatile signed __int32 *)(Context + 1808), 0, 0),
                v8 - v9,
                (unsigned int)v15,
                (__int64)v14,
                v12,
                v11,
                *(_BYTE *)(Context + 2056));
          }
        }
      }
    }
  }
LABEL_21:
  *(_QWORD *)(Context + 368) = MmBadPointer;
  *(_DWORD *)(Context + 376) = 1;
  HIDSM_AddHidsmEvent(Context, 2031);
  CompleteAllCollectionWaitWakeIrps(Context, 0);
}

```

## disassembly

```asm
0x18001b4f0  push    rbx
0x18001b4f2  push    rbp
0x18001b4f3  push    rsi
0x18001b4f4  push    rdi
0x18001b4f5  sub     rsp, 0B8h
0x18001b4fc  mov     rax, cs:__security_cookie
0x18001b503  xor     rax, rsp
0x18001b506  mov     [rsp+0D8h+var_38], rax
0x18001b50e  mov     rbx, r9
0x18001b511  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x18001b516  mov     rdi, [rsp+0D8h+IoStatus]
0x18001b51e  xor     esi, esi
0x18001b520  mov     ebp, 1
0x18001b525  test    eax, eax
0x18001b527  jnz     short loc_18001B537
0x18001b529  test    rdi, rdi
0x18001b52c  jz      loc_18001B6B0
0x18001b532  jmp     loc_18001B5CD
0x18001b537  test    rdi, rdi
0x18001b53a  jz      loc_18001B6B0
0x18001b540  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b547  lea     rax, WPP_GLOBAL_Control
0x18001b54e  cmp     rcx, rax
0x18001b551  jz      short loc_18001B565
0x18001b553  test    dword ptr [rcx+2Ch], 100h
0x18001b55a  jz      short loc_18001B565
0x18001b55c  cmp     byte ptr [rcx+29h], 4
0x18001b560  mov     dl, bpl
0x18001b563  jnb     short loc_18001B568
0x18001b565  mov     dl, sil
0x18001b568  lea     rax, WPP_RECORDER_INITIALIZED
0x18001b56f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001b576  setnz   r8b
0x18001b57a  test    dl, dl
0x18001b57c  jnz     short loc_18001B583
0x18001b57e  test    r8b, r8b
0x18001b581  jz      short loc_18001B5CD
0x18001b583  mov     eax, [rdi]
0x18001b585  mov     r9, [rbx+2A0h]
0x18001b58c  mov     rcx, [rcx+18h]
0x18001b590  mov     [rsp+0D8h+var_88], eax
0x18001b594  mov     rax, [rbx+170h]
0x18001b59b  mov     [rsp+0D8h+var_90], rax
0x18001b5a0  mov     rax, [rbx]
0x18001b5a3  mov     [rsp+0D8h+var_98], rax
0x18001b5a8  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x18001b5af  mov     [rsp+0D8h+var_A0], rax
0x18001b5b4  mov     word ptr [rsp+0D8h+var_A8], 2Bh ; '+'
0x18001b5bb  mov     [rsp+0D8h+var_B0], 9
0x18001b5c3  mov     byte ptr [rsp+0D8h+var_B8], 4
0x18001b5c8  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x18001b5cd  cmp     [rdi], esi
0x18001b5cf  jl      loc_18001B6B0
0x18001b5d5  cmp     [rbx+6F0h], esi
0x18001b5db  jz      loc_18001B6B0
0x18001b5e1  mov     r8, 0FFFFF78000000014h
0x18001b5eb  mov     ecx, esi
0x18001b5ed  xor     eax, eax
0x18001b5ef  mov     r8, [r8]
0x18001b5f2  lock cmpxchg [rbx+718h], ecx
0x18001b5fa  mov     r9, [rbx+98h]
0x18001b601  movsxd  rdi, eax
0x18001b604  test    r9, r9
0x18001b607  jz      loc_18001B6B0
0x18001b60d  mov     rcx, cs:MmBadPointer
0x18001b614  cmp     r9, [rcx]
0x18001b617  jz      loc_18001B6B0
0x18001b61d  mov     r11d, [rbx+0A8h]
0x18001b624  mov     r10d, esi
0x18001b627  test    r11d, r11d
0x18001b62a  jz      loc_18001B6B0
0x18001b630  cmp     r10w, 10h
0x18001b635  jnb     short loc_18001B668
0x18001b637  movzx   edx, r10w
0x18001b63b  add     r10w, bp
0x18001b63f  imul    rcx, rdx, 1A8h
0x18001b646  movzx   eax, word ptr [rcx+r9+0Ah]
0x18001b64c  mov     [rsp+rdx*2+0D8h+var_58], ax
0x18001b654  movzx   eax, word ptr [rcx+r9+8]
0x18001b65a  mov     [rsp+rdx*2+0D8h+var_78], ax
0x18001b65f  movzx   eax, r10w
0x18001b663  cmp     eax, r11d
0x18001b666  jb      short loc_18001B630
0x18001b668  test    r10w, r10w
0x18001b66c  jz      short loc_18001B6B0
0x18001b66e  mov     r9b, [rbx+808h]
0x18001b675  sub     r8, rdi
0x18001b678  xor     eax, eax
0x18001b67a  mov     ecx, esi
0x18001b67c  lock cmpxchg [rbx+710h], ecx
0x18001b684  mov     byte ptr [rsp+0D8h+var_A0], r9b
0x18001b689  mov     edx, eax
0x18001b68b  mov     [rsp+0D8h+var_A8], r11d
0x18001b690  lea     rax, [rsp+0D8h+var_78]
0x18001b695  mov     word ptr [rsp+0D8h+var_B0], r10w
0x18001b69b  lea     r9, [rsp+0D8h+var_58]
0x18001b6a3  mov     rcx, rbx
0x18001b6a6  mov     [rsp+0D8h+var_B8], rax
0x18001b6ab  call    TraceLoggingWaitWakeCompletedInSuppressInput
0x18001b6b0  mov     rax, cs:MmBadPointer
0x18001b6b7  mov     rcx, rbx
0x18001b6ba  mov     rdx, [rax]
0x18001b6bd  mov     [rbx+170h], rdx
0x18001b6c4  mov     edx, 7EFh
0x18001b6c9  mov     [rbx+178h], ebp
0x18001b6cf  call    HIDSM_AddHidsmEvent
0x18001b6d4  xor     edx, edx
0x18001b6d6  mov     rcx, rbx
0x18001b6d9  call    CompleteAllCollectionWaitWakeIrps
0x18001b6de  mov     rcx, [rsp+0D8h+var_38]
0x18001b6e6  xor     rcx, rsp; StackCookie
0x18001b6e9  call    __security_check_cookie
0x18001b6ee  add     rsp, 0B8h
0x18001b6f5  pop     rdi
0x18001b6f6  pop     rsi
0x18001b6f7  pop     rbp
0x18001b6f8  pop     rbx
0x18001b6f9  retn
```
