# ATL::CAtlExeModuleT<CcttunesvrModule>::Unlock(void)

- ea: `0x1400061b0`
- end: `0x1400061f3`
- name: `?Unlock@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@UEAAJXZ`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400061b0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400061d0`
- `KERNEL32!SetEvent` at `0x1400061d0`
- `USER32!PostThreadMessageW` at `0x1400061e5`
- `USER32!PostThreadMessageW` at `0x1400061e5`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CcttunesvrModule>::Unlock(__int64 a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 12));
  if ( !v1 )
  {
    if ( *(_BYTE *)(a1 + 96) )
    {
      *(_BYTE *)(a1 + 97) = 1;
      SetEvent(*(HANDLE *)(a1 + 80));
    }
    else
    {
      PostThreadMessageW(*(_DWORD *)(a1 + 72), 0x12u, 0, 0);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400061b0  push    rbx
0x1400061b2  sub     rsp, 20h
0x1400061b6  or      ebx, 0FFFFFFFFh
0x1400061b9  lock xadd [rcx+0Ch], ebx
0x1400061be  sub     ebx, 1
0x1400061c1  jnz     short loc_1400061EB
0x1400061c3  cmp     [rcx+60h], bl
0x1400061c6  jz      short loc_1400061D8
0x1400061c8  mov     byte ptr [rcx+61h], 1
0x1400061cc  mov     rcx, [rcx+50h]; hEvent
0x1400061d0  call    cs:__imp_SetEvent
0x1400061d6  jmp     short loc_1400061EB
0x1400061d8  mov     ecx, [rcx+48h]; idThread
0x1400061db  xor     r9d, r9d; lParam
0x1400061de  xor     r8d, r8d; wParam
0x1400061e1  lea     edx, [r9+12h]; Msg
0x1400061e5  call    cs:__imp_PostThreadMessageW
0x1400061eb  mov     eax, ebx
0x1400061ed  add     rsp, 20h
0x1400061f1  pop     rbx
0x1400061f2  retn
```
