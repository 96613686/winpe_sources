# CVolumeCacheCallBack::PurgeProgress(unsigned __int64,unsigned __int64,ulong,ushort const *)

- ea: `0x1400057b0`
- end: `0x1400057f5`
- name: `?PurgeProgress@CVolumeCacheCallBack@@UEAAJ_K0KPEBG@Z`
- size: `69`
- prototype: `__int64 __fastcall(CVolumeCacheCallBack *this, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `USER32!PostMessageW` at `0x1400057d4`
- `USER32!PostMessageW` at `0x1400057d4`

## pseudocode

```c
__int64 __fastcall CVolumeCacheCallBack::PurgeProgress(CVolumeCacheCallBack *this, __int64 a2)
{
  __int64 v2; // rcx

  v2 = qword_140021680;
  *(_QWORD *)(qword_140021680 + 1728) = a2;
  PostMessageW(*(HWND *)(v2 + 1696), 0x401u, 0, 0);
  return *(_DWORD *)(qword_140021680 + 1772) != 0 ? 0x80004004 : 0;
}

```

## disassembly

```asm
0x1400057b0  sub     rsp, 28h
0x1400057b4  mov     rcx, cs:qword_140021680
0x1400057bb  xor     r9d, r9d; lParam
0x1400057be  xor     r8d, r8d; wParam
0x1400057c1  mov     [rcx+6C0h], rdx
0x1400057c8  mov     edx, 401h; Msg
0x1400057cd  mov     rcx, [rcx+6A0h]; hWnd
0x1400057d4  call    cs:__imp_PostMessageW
0x1400057da  mov     rax, cs:qword_140021680
0x1400057e1  mov     ecx, [rax+6ECh]
0x1400057e7  neg     ecx
0x1400057e9  sbb     eax, eax
0x1400057eb  and     eax, 80004004h
0x1400057f0  add     rsp, 28h
0x1400057f4  retn
```
