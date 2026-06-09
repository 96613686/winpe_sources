# ATL::CAtlExeModuleT<HostExeModule>::Unlock(void)

- ea: `0x140007820`
- end: `0x140007863`
- name: `?Unlock@?$CAtlExeModuleT@VHostExeModule@@@ATL@@UEAAJXZ`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007820`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140007840`
- `KERNEL32!SetEvent` at `0x140007840`
- `USER32!PostThreadMessageW` at `0x140007855`
- `USER32!PostThreadMessageW` at `0x140007855`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<HostExeModule>::Unlock(__int64 a1)
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
0x140007820  push    rbx
0x140007822  sub     rsp, 20h
0x140007826  or      ebx, 0FFFFFFFFh
0x140007829  lock xadd [rcx+0Ch], ebx
0x14000782e  sub     ebx, 1
0x140007831  jnz     short loc_14000785B
0x140007833  cmp     [rcx+60h], bl
0x140007836  jz      short loc_140007848
0x140007838  mov     byte ptr [rcx+61h], 1
0x14000783c  mov     rcx, [rcx+50h]; hEvent
0x140007840  call    cs:__imp_SetEvent
0x140007846  jmp     short loc_14000785B
0x140007848  mov     ecx, [rcx+48h]; idThread
0x14000784b  xor     r9d, r9d; lParam
0x14000784e  xor     r8d, r8d; wParam
0x140007851  lea     edx, [r9+12h]; Msg
0x140007855  call    cs:__imp_PostThreadMessageW
0x14000785b  mov     eax, ebx
0x14000785d  add     rsp, 20h
0x140007861  pop     rbx
0x140007862  retn
```
