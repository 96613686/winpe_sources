# IMSVidEVRImpl<CMSVidEVR,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidEVR>::PostStop(void)

- ea: `0x1800eb8e0`
- end: `0x1800eb96f`
- name: `?PostStop@?$IMSVidEVRImpl@VCMSVidEVR@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BUIMSVidEVR@@@@UEAAJXZ`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800eb8e0`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x1800eb934`
- `KERNEL32!SetThreadExecutionState` at `0x1800eb934`
- `USER32!SystemParametersInfoW` at `0x1800eb90d`
- `USER32!SystemParametersInfoW` at `0x1800eb923`
- `USER32!SystemParametersInfoW` at `0x1800eb90d`
- `USER32!SystemParametersInfoW` at `0x1800eb923`

## pseudocode

```c
__int64 __fastcall IMSVidEVRImpl<CMSVidEVR,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidEVR>::PostStop(
        __int64 a1)
{
  __int64 result; // rax
  unsigned int v3; // [rsp+20h] [rbp-28h] BYREF
  ComException *v4; // [rsp+28h] [rbp-20h] BYREF
  std::bad_alloc *v5; // [rsp+30h] [rbp-18h] BYREF
  std::exception *v6; // [rsp+38h] [rbp-10h] BYREF

  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  if ( *(_BYTE *)(a1 + 73) )
  {
    SystemParametersInfoW(0x1025u, 0, (PVOID)(a1 + 76), 0);
    SystemParametersInfoW(0x4Bu, *(_DWORD *)(a1 + 80), 0, 3u);
  }
  if ( *(_BYTE *)(a1 + 92) )
    SetThreadExecutionState(0x80000000);
  try
  {
    result = (*(__int64 (**)(void))(*(_QWORD *)a1 + 200LL))();
  }
  catch ( long v3 )
  {
    return v3;
  }
  catch ( ComException *v4 )
  {
    return *(unsigned int *)v4;
  }
  catch ( std::bad_alloc *v5 )
  {
    return 2147942414LL;
  }
  catch ( std::exception *v6 )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800eb8e0  push    rbx
0x1800eb8e2  sub     rsp, 40h
0x1800eb8e6  mov     rbx, rcx
0x1800eb8e9  xorps   xmm0, xmm0
0x1800eb8ec  movdqu  xmmword ptr [rcx+30h], xmm0
0x1800eb8f1  xorps   xmm1, xmm1
0x1800eb8f4  movdqu  xmmword ptr [rcx+20h], xmm1
0x1800eb8f9  cmp     byte ptr [rcx+49h], 0
0x1800eb8fd  jz      short loc_1800EB929
0x1800eb8ff  lea     r8, [rcx+4Ch]; pvParam
0x1800eb903  xor     r9d, r9d; fWinIni
0x1800eb906  xor     edx, edx; uiParam
0x1800eb908  mov     ecx, 1025h; uiAction
0x1800eb90d  call    cs:__imp_SystemParametersInfoW
0x1800eb913  mov     r9d, 3; fWinIni
0x1800eb919  xor     r8d, r8d; pvParam
0x1800eb91c  mov     edx, [rbx+50h]; uiParam
0x1800eb91f  lea     ecx, [r9+48h]; uiAction
0x1800eb923  call    cs:__imp_SystemParametersInfoW
0x1800eb929  cmp     byte ptr [rbx+5Ch], 0
0x1800eb92d  jz      short loc_1800EB93A
0x1800eb92f  mov     ecx, 80000000h; esFlags
0x1800eb934  call    cs:__imp_SetThreadExecutionState
0x1800eb93a  mov     rax, [rbx]
0x1800eb93d  xor     edx, edx
0x1800eb93f  mov     rcx, rbx
0x1800eb942  mov     rax, [rax+0C8h]
0x1800eb949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb94e  jmp     short loc_1800EB968
0x1800eb950  mov     eax, [rsp+48h+var_28]
0x1800eb954  jmp     short loc_1800EB968
0x1800eb956  mov     eax, [rsp+48h+arg_0]
0x1800eb95a  jmp     short loc_1800EB968
0x1800eb95c  mov     eax, 8007000Eh
0x1800eb961  jmp     short loc_1800EB968
0x1800eb963  mov     eax, 8000FFFFh
0x1800eb968  add     rsp, 40h
0x1800eb96c  pop     rbx
0x1800eb96d  retn
```
