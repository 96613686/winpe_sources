# FwHyperVMgrConvertRuleContainerMetadata

- ea: `0x18007d0e4`
- end: `0x18007d2b0`
- name: `FwHyperVMgrConvertRuleContainerMetadata`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007ddc0`

## callees

- `0x18000ae9c`
- `0x18000af3c`
- `0x1800670c0`
- `0x18007d0e4`

## import_xrefs

- `fwbase!FwStringCopy` at `0x18007d1aa`
- `fwbase!FwStringCopy` at `0x18007d1ca`
- `fwbase!FwStringCopy` at `0x18007d1aa`
- `fwbase!FwStringCopy` at `0x18007d1ca`
- `fwbase!FwAlloc` at `0x18007d11a`
- `fwbase!FwAlloc` at `0x18007d11a`
- `fwbase!FwFree` at `0x18007d255`
- `fwbase!FwFree` at `0x18007d260`
- `fwbase!FwFree` at `0x18007d271`
- `fwbase!FwFree` at `0x18007d255`
- `fwbase!FwFree` at `0x18007d260`
- `fwbase!FwFree` at `0x18007d271`

## string_xrefs

- `0x18007d280`: `mpssvc.dll`
- `0x18007d223`: `FwStringCopy:switchName`
- `0x18007d1fc`: `FwStringCopy:portName`

## pseudocode

```c
__int64 __fastcall FwHyperVMgrConvertRuleContainerMetadata(__int64 a1, __int64 a2)
{
  int v2; // edi
  __int64 v4; // rax
  __int64 v6; // rsi
  __int64 *v7; // r12
  __int64 v8; // rbx
  __int64 *v9; // r14
  unsigned __int64 v10; // rbp
  __int64 v11; // r13
  __int64 v12; // rcx
  int v13; // edx
  const char *v14; // rax
  unsigned __int64 i; // r14
  __int64 v17; // [rsp+80h] [rbp+8h]

  v2 = 0;
  v4 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3;
  if ( v4 )
  {
    v6 = FwAlloc(24 * v4);
    if ( v6 )
    {
      v7 = *(__int64 **)(a1 + 16);
      v8 = 0;
      v9 = *(__int64 **)(a1 + 8);
      v10 = v7 - v9;
      while ( v9 != v7 )
      {
        v11 = *v9;
        v17 = v6 + 24 * v8;
        *(_DWORD *)(v17 + 16) = *(_DWORD *)(*v9 + 12);
        v2 = FwStringCopy(*(_QWORD *)(*(_QWORD *)v11 + 8LL), v17);
        if ( v2 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 15;
            v14 = "FwStringCopy:switchName";
LABEL_17:
            WPP_SF_Ds(
              *(_QWORD *)(v12 + 16),
              v13,
              (unsigned int)WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
              v2,
              (__int64)v14);
          }
LABEL_18:
          for ( i = 0; i < v10; ++i )
          {
            FwFree(*(_QWORD *)(v6 + 24 * i));
            FwFree(*(_QWORD *)(v6 + 24 * i + 8));
          }
          FwFree(v6);
          return (unsigned int)v2;
        }
        v2 = FwStringCopy(*(_QWORD *)(*(_QWORD *)v11 + 16LL), v17 + 8);
        if ( v2 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 16;
            v14 = "FwStringCopy:portName";
            goto LABEL_17;
          }
          goto LABEL_18;
        }
        v8 = (unsigned int)(v8 + 1);
        ++v9;
      }
      if ( v10 != (unsigned int)v8 )
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)v10, (unsigned int)v8);
      *(_QWORD *)(a2 + 280) = v6;
      *(_DWORD *)(a2 + 272) = v8;
    }
    else
    {
      v2 = -2147024882;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
          2147942414LL);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18007d0e4  push    rbx
0x18007d0e6  push    rbp
0x18007d0e7  push    rsi
0x18007d0e8  push    rdi
0x18007d0e9  push    r12
0x18007d0eb  push    r13
0x18007d0ed  push    r14
0x18007d0ef  push    r15
0x18007d0f1  sub     rsp, 38h
0x18007d0f5  mov     rax, [rcx+10h]
0x18007d0f9  xor     edi, edi
0x18007d0fb  sub     rax, [rcx+8]
0x18007d0ff  mov     r15, rdx
0x18007d102  sar     rax, 3
0x18007d106  mov     rbp, rcx
0x18007d109  test    rax, rax
0x18007d10c  jz      loc_18007D29D
0x18007d112  lea     rcx, [rax+rax*2]
0x18007d116  shl     rcx, 3
0x18007d11a  call    cs:__imp_FwAlloc
0x18007d120  mov     rsi, rax
0x18007d123  test    rax, rax
0x18007d126  jnz     short loc_18007D169
0x18007d128  mov     edi, 8007000Eh
0x18007d12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d134  lea     rax, WPP_GLOBAL_Control
0x18007d13b  cmp     rcx, rax
0x18007d13e  jz      loc_18007D29D
0x18007d144  test    byte ptr [rcx+1Ch], 1
0x18007d148  jz      loc_18007D29D
0x18007d14e  mov     rcx, [rcx+10h]
0x18007d152  lea     edx, [rsi+0Eh]
0x18007d155  mov     r9d, edi
0x18007d158  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d15f  call    WPP_SF_d
0x18007d164  jmp     loc_18007D29D
0x18007d169  mov     r12, [rbp+10h]
0x18007d16d  xor     ebx, ebx
0x18007d16f  mov     r14, [rbp+8]
0x18007d173  mov     rbp, r12
0x18007d176  sub     rbp, r14
0x18007d179  sar     rbp, 3
0x18007d17d  mov     eax, ebx
0x18007d17f  cmp     r14, r12
0x18007d182  jz      loc_18007D279
0x18007d188  mov     r13, [r14]
0x18007d18b  lea     rax, [rbx+rbx*2]
0x18007d18f  lea     rdx, [rsi+rax*8]
0x18007d193  mov     [rsp+78h+arg_0], rdx
0x18007d19b  mov     eax, [r13+0Ch]
0x18007d19f  mov     [rdx+10h], eax
0x18007d1a2  mov     rcx, [r13+0]
0x18007d1a6  mov     rcx, [rcx+8]
0x18007d1aa  call    cs:__imp_FwStringCopy
0x18007d1b0  mov     edi, eax
0x18007d1b2  test    eax, eax
0x18007d1b4  js      short loc_18007D205
0x18007d1b6  mov     rcx, [r13+0]
0x18007d1ba  mov     rdx, [rsp+78h+arg_0]
0x18007d1c2  add     rdx, 8
0x18007d1c6  mov     rcx, [rcx+10h]
0x18007d1ca  call    cs:__imp_FwStringCopy
0x18007d1d0  mov     edi, eax
0x18007d1d2  test    eax, eax
0x18007d1d4  js      short loc_18007D1DE
0x18007d1d6  inc     ebx
0x18007d1d8  add     r14, 8
0x18007d1dc  jmp     short loc_18007D17D
0x18007d1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d1e5  lea     rax, WPP_GLOBAL_Control
0x18007d1ec  cmp     rcx, rax
0x18007d1ef  jz      short loc_18007D242
0x18007d1f1  test    byte ptr [rcx+1Ch], 1
0x18007d1f5  jz      short loc_18007D242
0x18007d1f7  mov     edx, 10h
0x18007d1fc  lea     rax, aFwstringcopyPo; "FwStringCopy:portName"
0x18007d203  jmp     short loc_18007D22A
0x18007d205  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d20c  lea     rax, WPP_GLOBAL_Control
0x18007d213  cmp     rcx, rax
0x18007d216  jz      short loc_18007D242
0x18007d218  test    byte ptr [rcx+1Ch], 1
0x18007d21c  jz      short loc_18007D242
0x18007d21e  mov     edx, 0Fh
0x18007d223  lea     rax, aFwstringcopySw; "FwStringCopy:switchName"
0x18007d22a  mov     rcx, [rcx+10h]
0x18007d22e  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d235  mov     r9d, edi
0x18007d238  mov     [rsp+78h+var_58], rax
0x18007d23d  call    WPP_SF_Ds
0x18007d242  xor     r14d, r14d
0x18007d245  mov     r15, rsi
0x18007d248  test    rbp, rbp
0x18007d24b  jz      short loc_18007D26E
0x18007d24d  lea     rbx, [r14+r14*2]
0x18007d251  mov     rcx, [r15+rbx*8]
0x18007d255  call    cs:__imp_FwFree
0x18007d25b  mov     rcx, [r15+rbx*8+8]
0x18007d260  call    cs:__imp_FwFree
0x18007d266  inc     r14
0x18007d269  cmp     r14, rbp
0x18007d26c  jb      short loc_18007D24D
0x18007d26e  mov     rcx, rsi
0x18007d271  call    cs:__imp_FwFree
0x18007d277  jmp     short loc_18007D29D
0x18007d279  cmp     rbp, rax
0x18007d27c  jz      short loc_18007D28F
0x18007d27e  mov     edx, ebp
0x18007d280  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18007d287  mov     r8d, ebx
0x18007d28a  call    MicrosoftTelemetryAssertTriggeredArgs
0x18007d28f  mov     [r15+118h], rsi
0x18007d296  mov     [r15+110h], ebx
0x18007d29d  mov     eax, edi
0x18007d29f  add     rsp, 38h
0x18007d2a3  pop     r15
0x18007d2a5  pop     r14
0x18007d2a7  pop     r13
0x18007d2a9  pop     r12
0x18007d2ab  pop     rdi
0x18007d2ac  pop     rsi
0x18007d2ad  pop     rbp
0x18007d2ae  pop     rbx
0x18007d2af  retn
```
