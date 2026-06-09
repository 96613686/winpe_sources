# FwHyperVMgrConvertRuleContainerMetadata

- ea: `0x180081058`
- end: `0x180081249`
- name: `FwHyperVMgrConvertRuleContainerMetadata`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180081d9c`

## callees

- `0x18000a66c`
- `0x18000a710`
- `0x18006a710`
- `0x180081058`

## import_xrefs

- `fwbase!FwStringCopy` at `0x180081124`
- `fwbase!FwStringCopy` at `0x18008114a`
- `fwbase!FwStringCopy` at `0x180081124`
- `fwbase!FwStringCopy` at `0x18008114a`
- `fwbase!FwAlloc` at `0x18008108e`
- `fwbase!FwAlloc` at `0x18008108e`
- `fwbase!FwFree` at `0x1800811db`
- `fwbase!FwFree` at `0x1800811ec`
- `fwbase!FwFree` at `0x180081203`
- `fwbase!FwFree` at `0x1800811db`
- `fwbase!FwFree` at `0x1800811ec`
- `fwbase!FwFree` at `0x180081203`

## string_xrefs

- `0x180081218`: `mpssvc.dll`
- `0x1800811a9`: `FwStringCopy:switchName`
- `0x180081182`: `FwStringCopy:portName`

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
0x180081058  push    rbx
0x18008105a  push    rbp
0x18008105b  push    rsi
0x18008105c  push    rdi
0x18008105d  push    r12
0x18008105f  push    r13
0x180081061  push    r14
0x180081063  push    r15
0x180081065  sub     rsp, 38h
0x180081069  mov     rax, [rcx+10h]
0x18008106d  xor     edi, edi
0x18008106f  sub     rax, [rcx+8]
0x180081073  mov     r15, rdx
0x180081076  sar     rax, 3
0x18008107a  mov     rbp, rcx
0x18008107d  test    rax, rax
0x180081080  jz      loc_180081235
0x180081086  lea     rcx, [rax+rax*2]
0x18008108a  shl     rcx, 3
0x18008108e  call    cs:__imp_FwAlloc
0x180081095  nop     dword ptr [rax+rax+00h]
0x18008109a  mov     rsi, rax
0x18008109d  test    rax, rax
0x1800810a0  jnz     short loc_1800810E3
0x1800810a2  mov     edi, 8007000Eh
0x1800810a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800810ae  lea     rax, WPP_GLOBAL_Control
0x1800810b5  cmp     rcx, rax
0x1800810b8  jz      loc_180081235
0x1800810be  test    byte ptr [rcx+1Ch], 1
0x1800810c2  jz      loc_180081235
0x1800810c8  mov     rcx, [rcx+10h]
0x1800810cc  lea     edx, [rsi+0Eh]
0x1800810cf  mov     r9d, edi
0x1800810d2  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800810d9  call    WPP_SF_d
0x1800810de  jmp     loc_180081235
0x1800810e3  mov     r12, [rbp+10h]
0x1800810e7  xor     ebx, ebx
0x1800810e9  mov     r14, [rbp+8]
0x1800810ed  mov     rbp, r12
0x1800810f0  sub     rbp, r14
0x1800810f3  sar     rbp, 3
0x1800810f7  mov     eax, ebx
0x1800810f9  cmp     r14, r12
0x1800810fc  jz      loc_180081211
0x180081102  mov     r13, [r14]
0x180081105  lea     rax, [rbx+rbx*2]
0x180081109  lea     rdx, [rsi+rax*8]
0x18008110d  mov     [rsp+78h+arg_0], rdx
0x180081115  mov     eax, [r13+0Ch]
0x180081119  mov     [rdx+10h], eax
0x18008111c  mov     rcx, [r13+0]
0x180081120  mov     rcx, [rcx+8]
0x180081124  call    cs:__imp_FwStringCopy
0x18008112b  nop     dword ptr [rax+rax+00h]
0x180081130  mov     edi, eax
0x180081132  test    eax, eax
0x180081134  js      short loc_18008118B
0x180081136  mov     rcx, [r13+0]
0x18008113a  mov     rdx, [rsp+78h+arg_0]
0x180081142  add     rdx, 8
0x180081146  mov     rcx, [rcx+10h]
0x18008114a  call    cs:__imp_FwStringCopy
0x180081151  nop     dword ptr [rax+rax+00h]
0x180081156  mov     edi, eax
0x180081158  test    eax, eax
0x18008115a  js      short loc_180081164
0x18008115c  inc     ebx
0x18008115e  add     r14, 8
0x180081162  jmp     short loc_1800810F7
0x180081164  mov     rcx, cs:WPP_GLOBAL_Control
0x18008116b  lea     rax, WPP_GLOBAL_Control
0x180081172  cmp     rcx, rax
0x180081175  jz      short loc_1800811C8
0x180081177  test    byte ptr [rcx+1Ch], 1
0x18008117b  jz      short loc_1800811C8
0x18008117d  mov     edx, 10h
0x180081182  lea     rax, aFwstringcopyPo; "FwStringCopy:portName"
0x180081189  jmp     short loc_1800811B0
0x18008118b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081192  lea     rax, WPP_GLOBAL_Control
0x180081199  cmp     rcx, rax
0x18008119c  jz      short loc_1800811C8
0x18008119e  test    byte ptr [rcx+1Ch], 1
0x1800811a2  jz      short loc_1800811C8
0x1800811a4  mov     edx, 0Fh
0x1800811a9  lea     rax, aFwstringcopySw; "FwStringCopy:switchName"
0x1800811b0  mov     rcx, [rcx+10h]
0x1800811b4  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800811bb  mov     r9d, edi
0x1800811be  mov     [rsp+78h+var_58], rax
0x1800811c3  call    WPP_SF_Ds
0x1800811c8  xor     r14d, r14d
0x1800811cb  mov     r15, rsi
0x1800811ce  test    rbp, rbp
0x1800811d1  jz      short loc_180081200
0x1800811d3  lea     rbx, [r14+r14*2]
0x1800811d7  mov     rcx, [r15+rbx*8]
0x1800811db  call    cs:__imp_FwFree
0x1800811e2  nop     dword ptr [rax+rax+00h]
0x1800811e7  mov     rcx, [r15+rbx*8+8]
0x1800811ec  call    cs:__imp_FwFree
0x1800811f3  nop     dword ptr [rax+rax+00h]
0x1800811f8  inc     r14
0x1800811fb  cmp     r14, rbp
0x1800811fe  jb      short loc_1800811D3
0x180081200  mov     rcx, rsi
0x180081203  call    cs:__imp_FwFree
0x18008120a  nop     dword ptr [rax+rax+00h]
0x18008120f  jmp     short loc_180081235
0x180081211  cmp     rbp, rax
0x180081214  jz      short loc_180081227
0x180081216  mov     edx, ebp; __annotation("Debug", "TelemetryAssert", "totalMetadataCount == metadataCount")
0x180081218  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18008121f  mov     r8d, ebx
0x180081222  call    MicrosoftTelemetryAssertTriggeredArgs
0x180081227  mov     [r15+118h], rsi
0x18008122e  mov     [r15+110h], ebx
0x180081235  mov     eax, edi
0x180081237  add     rsp, 38h
0x18008123b  pop     r15
0x18008123d  pop     r14
0x18008123f  pop     r13
0x180081241  pop     r12
0x180081243  pop     rdi
0x180081244  pop     rsi
0x180081245  pop     rbp
0x180081246  pop     rbx
0x180081247  retn
```
