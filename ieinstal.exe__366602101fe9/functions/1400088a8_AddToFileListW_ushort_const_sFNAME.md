# AddToFileListW(ushort const *,sFNAME * *)

- ea: `0x1400088a8`
- end: `0x1400088ff`
- name: `?AddToFileListW@@YAJPEBGPEAPEAUsFNAME@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sFNAME **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140004e20`
- `0x14000747c`

## callees

- `0x140008740`
- `0x1400088a8`
- `0x14000bc68`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400088e5`
- `ole32!CoTaskMemFree` at `0x1400088e5`

## pseudocode

```c
__int64 __fastcall AddToFileListW(const unsigned __int16 *a1, struct sFNAME **a2)
{
  int v3; // ebx
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  pv = 0;
  v3 = WSZtoSZ((__int64)a1, a1, (char **)&pv);
  if ( v3 >= 0 )
  {
    v3 = AddToFileListA((const char *)pv, a2);
    CoTaskMemFree(pv);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400088a8  mov     [rsp+arg_0], rbx
0x1400088ad  push    rdi
0x1400088ae  sub     rsp, 20h
0x1400088b2  mov     rdi, rdx
0x1400088b5  mov     [rsp+28h+pv], 0
0x1400088be  mov     rdx, rcx; unsigned __int16 *
0x1400088c1  lea     r8, [rsp+28h+pv]; char **
0x1400088c6  call    ?WSZtoSZ@@YAJIPEBGPEAPEAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x1400088cb  mov     ebx, eax
0x1400088cd  test    eax, eax
0x1400088cf  js      short loc_1400088F1
0x1400088d1  mov     rcx, [rsp+28h+pv]; char *
0x1400088d6  mov     rdx, rdi; struct sFNAME **
0x1400088d9  call    ?AddToFileListA@@YAJPEBDPEAPEAUsFNAME@@@Z; AddToFileListA(char const *,sFNAME * *)
0x1400088de  mov     rcx, [rsp+28h+pv]; pv
0x1400088e3  mov     ebx, eax
0x1400088e5  call    cs:__imp_CoTaskMemFree
0x1400088ec  nop     dword ptr [rax+rax+00h]
0x1400088f1  mov     eax, ebx
0x1400088f3  mov     rbx, [rsp+28h+arg_0]
0x1400088f8  add     rsp, 20h
0x1400088fc  pop     rdi
0x1400088fd  retn
```
