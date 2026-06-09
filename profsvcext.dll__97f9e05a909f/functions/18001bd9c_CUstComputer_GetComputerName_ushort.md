# CUstComputer::_GetComputerName(ushort * *)

- ea: `0x18001bd9c`
- end: `0x18001be5d`
- name: `?_GetComputerName@CUstComputer@@KAJPEAPEAG@Z`
- size: `193`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bb38`

## callees

- `0x18000baec`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001bd9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be0f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001be05`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001be05`

## pseudocode

```c
__int64 __fastcall CUstComputer::_GetComputerName(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rax
  __int64 v3; // r9
  unsigned int v4; // ebx
  signed int LastError; // eax
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  nSize = 16;
  v2 = (unsigned __int16 *)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = v2;
  if ( v2 )
  {
    v4 = 0;
    if ( !GetComputerNameW(v2, &nSize) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v4);
      }
    }
  }
  else
  {
    v4 = -2147024882;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v3);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001bd9c  push    rbx
0x18001bd9e  sub     rsp, 20h
0x18001bda2  mov     rbx, rcx
0x18001bda5  mov     [rsp+28h+nSize], 10h
0x18001bdad  mov     ecx, 20h ; ' '; unsigned __int64
0x18001bdb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bdb9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bdbe  mov     [rbx], rax
0x18001bdc1  test    rax, rax
0x18001bdc4  jnz     short loc_18001BDFB
0x18001bdc6  mov     ebx, 8007000Eh
0x18001bdcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdd2  lea     rax, WPP_GLOBAL_Control
0x18001bdd9  cmp     rcx, rax
0x18001bddc  jz      short loc_18001BE55
0x18001bdde  test    byte ptr [rcx+1Ch], 1
0x18001bde2  jz      short loc_18001BE55
0x18001bde4  mov     rcx, [rcx+10h]
0x18001bde8  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001bdef  mov     edx, 0Ah
0x18001bdf4  call    WPP_SF_
0x18001bdf9  jmp     short loc_18001BE55
0x18001bdfb  lea     rdx, [rsp+28h+nSize]; nSize
0x18001be00  mov     rcx, rax; lpBuffer
0x18001be03  xor     ebx, ebx
0x18001be05  call    cs:__imp_GetComputerNameW
0x18001be0b  test    eax, eax
0x18001be0d  jnz     short loc_18001BE55
0x18001be0f  call    cs:__imp_GetLastError
0x18001be15  mov     ebx, eax
0x18001be17  test    eax, eax
0x18001be19  jle     short loc_18001BE24
0x18001be1b  movzx   ebx, ax
0x18001be1e  or      ebx, 80070000h
0x18001be24  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be2b  lea     rax, WPP_GLOBAL_Control
0x18001be32  cmp     rcx, rax
0x18001be35  jz      short loc_18001BE55
0x18001be37  test    byte ptr [rcx+1Ch], 1
0x18001be3b  jz      short loc_18001BE55
0x18001be3d  mov     rcx, [rcx+10h]
0x18001be41  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001be48  mov     edx, 0Bh
0x18001be4d  mov     r9d, ebx
0x18001be50  call    WPP_SF_d
0x18001be55  mov     eax, ebx
0x18001be57  add     rsp, 20h
0x18001be5b  pop     rbx
0x18001be5c  retn
```
