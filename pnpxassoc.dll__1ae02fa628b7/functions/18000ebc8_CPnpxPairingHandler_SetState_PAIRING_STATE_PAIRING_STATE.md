# CPnpxPairingHandler::SetState(_PAIRING_STATE,_PAIRING_STATE *)

- ea: `0x18000ebc8`
- end: `0x18000ed0e`
- name: `?SetState@CPnpxPairingHandler@@IEAAJW4_PAIRING_STATE@@PEAW42@@Z`
- size: `326`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d880`
- `0x18000d9d0`
- `0x18000dbc0`
- `0x18000e340`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000e870`
- `0x18000e9d0`

## callees

- `0x18000bc98`
- `0x18000bce4`
- `0x18000ebc8`
- `0x18000f134`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000eced`
- `KERNEL32!LeaveCriticalSection` at `0x18000eced`
- `KERNEL32!EnterCriticalSection` at `0x18000ec16`
- `KERNEL32!EnterCriticalSection` at `0x18000ec16`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::SetState(__int64 a1, int a2, _DWORD *a3, __int64 a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  bool v9; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x23u, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids, a4, a1);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36);
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1:
        goto LABEL_9;
      case 2:
        v9 = *(_DWORD *)(a1 + 120) != 1;
        goto LABEL_22;
      case 3:
        v9 = *(_DWORD *)(a1 + 120) != 2;
        goto LABEL_22;
      case 4:
        if ( (unsigned int)(*(_DWORD *)(a1 + 120) - 2) > 1 )
        {
          v7 = -2147467259;
          goto LABEL_28;
        }
        break;
      case 5:
        v8 = 4;
        goto LABEL_21;
      default:
        v8 = 6;
        if ( a2 == 6 )
        {
LABEL_9:
          v8 = 0;
LABEL_21:
          v9 = *(_DWORD *)(a1 + 120) != v8;
LABEL_22:
          v7 = v9 ? 0x80004005 : 0;
          if ( v7 )
            goto LABEL_28;
          break;
        }
        if ( a2 == 7 )
          goto LABEL_21;
        if ( a2 != 8 )
        {
          v7 = -2147024809;
          goto LABEL_28;
        }
        break;
    }
  }
  if ( a3 )
    *a3 = *(_DWORD *)(a1 + 120);
  *(_DWORD *)(a1 + 120) = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
LABEL_28:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  return v7;
}

```

## disassembly

```asm
0x18000ebc8  push    rbx
0x18000ebca  push    rbp
0x18000ebcb  push    rsi
0x18000ebcc  push    rdi
0x18000ebcd  push    r12
0x18000ebcf  push    r14
0x18000ebd1  sub     rsp, 38h
0x18000ebd5  mov     r14, r8
0x18000ebd8  mov     edi, edx
0x18000ebda  mov     rsi, rcx
0x18000ebdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebe4  lea     r12, WPP_GLOBAL_Control
0x18000ebeb  cmp     rcx, r12
0x18000ebee  jz      short loc_18000EC10
0x18000ebf0  cmp     byte ptr [rcx+19h], 4
0x18000ebf4  jb      short loc_18000EC10
0x18000ebf6  mov     rcx, [rcx+10h]
0x18000ebfa  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000ec01  mov     edx, 23h ; '#'
0x18000ec06  mov     [rsp+68h+var_48], rsi
0x18000ec0b  call    WPP_SF_sq
0x18000ec10  xor     ebx, ebx
0x18000ec12  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000ec16  call    cs:__imp_EnterCriticalSection
0x18000ec1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec23  cmp     rcx, r12
0x18000ec26  jz      short loc_18000EC45
0x18000ec28  cmp     byte ptr [rcx+19h], 4
0x18000ec2c  jb      short loc_18000EC45
0x18000ec2e  mov     eax, [rsi+78h]
0x18000ec31  lea     edx, [rbx+24h]
0x18000ec34  mov     rcx, [rcx+10h]
0x18000ec38  mov     [rsp+68h+var_40], edi
0x18000ec3c  mov     dword ptr [rsp+68h+var_48], eax
0x18000ec40  call    WPP_SF_sdd
0x18000ec45  test    edi, edi
0x18000ec47  jz      short loc_18000ECB0
0x18000ec49  mov     ecx, 1
0x18000ec4e  cmp     edi, ecx
0x18000ec50  jnz     short loc_18000EC56
0x18000ec52  xor     eax, eax
0x18000ec54  jmp     short loc_18000EC9F
0x18000ec56  mov     edx, 2
0x18000ec5b  cmp     edi, edx
0x18000ec5d  jnz     short loc_18000EC66
0x18000ec5f  sub     ecx, [rsi+78h]
0x18000ec62  neg     ecx
0x18000ec64  jmp     short loc_18000ECA4
0x18000ec66  cmp     edi, 3
0x18000ec69  jnz     short loc_18000EC72
0x18000ec6b  sub     edx, [rsi+78h]
0x18000ec6e  neg     edx
0x18000ec70  jmp     short loc_18000ECA4
0x18000ec72  cmp     edi, 4
0x18000ec75  jnz     short loc_18000EC87
0x18000ec77  mov     eax, [rsi+78h]
0x18000ec7a  sub     eax, edx
0x18000ec7c  cmp     eax, ecx
0x18000ec7e  jbe     short loc_18000ECB0
0x18000ec80  mov     ebx, 80004005h
0x18000ec85  jmp     short loc_18000ECE9
0x18000ec87  cmp     edi, 5
0x18000ec8a  jnz     short loc_18000EC91
0x18000ec8c  lea     eax, [rdi-1]
0x18000ec8f  jmp     short loc_18000EC9F
0x18000ec91  mov     eax, 6
0x18000ec96  cmp     edi, eax
0x18000ec98  jz      short loc_18000EC52
0x18000ec9a  cmp     edi, 7
0x18000ec9d  jnz     short loc_18000ED02
0x18000ec9f  sub     eax, [rsi+78h]
0x18000eca2  neg     eax
0x18000eca4  sbb     ebx, ebx
0x18000eca6  and     ebx, 80004005h
0x18000ecac  test    ebx, ebx
0x18000ecae  jnz     short loc_18000ECE9
0x18000ecb0  test    r14, r14
0x18000ecb3  jz      short loc_18000ECBB
0x18000ecb5  mov     eax, [rsi+78h]
0x18000ecb8  mov     [r14], eax
0x18000ecbb  mov     [rsi+78h], edi
0x18000ecbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecc5  cmp     rcx, r12
0x18000ecc8  jz      short loc_18000ECE9
0x18000ecca  cmp     byte ptr [rcx+19h], 4
0x18000ecce  jb      short loc_18000ECE9
0x18000ecd0  mov     rcx, [rcx+10h]
0x18000ecd4  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000ecdb  mov     edx, 25h ; '%'
0x18000ece0  mov     dword ptr [rsp+68h+var_48], edi
0x18000ece4  call    WPP_SF_sd
0x18000ece9  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000eced  call    cs:__imp_LeaveCriticalSection
0x18000ecf3  mov     eax, ebx
0x18000ecf5  add     rsp, 38h
0x18000ecf9  pop     r14
0x18000ecfb  pop     r12
0x18000ecfd  pop     rdi
0x18000ecfe  pop     rsi
0x18000ecff  pop     rbp
0x18000ed00  pop     rbx
0x18000ed01  retn
0x18000ed02  cmp     edi, 8
0x18000ed05  jz      short loc_18000ECB0
0x18000ed07  mov     ebx, 80070057h
0x18000ed0c  jmp     short loc_18000ECE9
```
