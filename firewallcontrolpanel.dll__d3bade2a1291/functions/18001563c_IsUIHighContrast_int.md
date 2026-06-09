# IsUIHighContrast(int *)

- ea: `0x18001563c`
- end: `0x18001569a`
- name: `?IsUIHighContrast@@YAHPEAH@Z`
- size: `94`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009794`
- `0x1800110d0`
- `0x180012030`
- `0x1800130d0`
- `0x180013960`
- `0x180016214`
- `0x18001acb0`
- `0x180021000`

## callees

- `0x18001563c`

## import_xrefs

- `USER32!GetSysColor` at `0x180015679`
- `USER32!GetSysColor` at `0x180015679`
- `USER32!SystemParametersInfoW` at `0x180015662`
- `USER32!SystemParametersInfoW` at `0x180015662`

## pseudocode

```c
__int64 __fastcall IsUIHighContrast(int *a1)
{
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  SystemParametersInfoW(0x42u, 0, &pvParam, 0);
  if ( (BYTE4(pvParam) & 1) == 0 )
    return 0;
  if ( a1 )
    *a1 = GetSysColor(5) == 0xFFFFFF;
  return 1;
}

```

## disassembly

```asm
0x18001563c  push    rbx
0x18001563e  sub     rsp, 30h
0x180015642  xor     edx, edx; uiParam
0x180015644  lea     r8, [rsp+38h+pvParam]; pvParam
0x180015649  xorps   xmm0, xmm0
0x18001564c  mov     rbx, rcx
0x18001564f  movups  [rsp+38h+pvParam], xmm0
0x180015654  xor     r9d, r9d; fWinIni
0x180015657  mov     dword ptr [rsp+38h+pvParam], 10h
0x18001565f  lea     ecx, [rdx+42h]; uiAction
0x180015662  call    cs:__imp_SystemParametersInfoW
0x180015668  test    byte ptr [rsp+38h+pvParam+4], 1
0x18001566d  jz      short loc_180015692
0x18001566f  test    rbx, rbx
0x180015672  jz      short loc_18001568B
0x180015674  mov     ecx, 5; nIndex
0x180015679  call    cs:__imp_GetSysColor
0x18001567f  xor     ecx, ecx
0x180015681  cmp     eax, 0FFFFFFh
0x180015686  setz    cl
0x180015689  mov     [rbx], ecx
0x18001568b  mov     eax, 1
0x180015690  jmp     short loc_180015694
0x180015692  xor     eax, eax
0x180015694  add     rsp, 30h
0x180015698  pop     rbx
0x180015699  retn
```
