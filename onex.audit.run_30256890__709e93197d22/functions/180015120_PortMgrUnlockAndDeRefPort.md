# PortMgrUnlockAndDeRefPort

- ea: `0x180015120`
- end: `0x18001520d`
- name: `PortMgrUnlockAndDeRefPort`
- size: `237`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180014e50`
- `0x180023d80`
- `0x18002c010`
- `0x18002c1f0`
- `0x18002c8d0`
- `0x18002cae0`
- `0x18002cd10`
- `0x18002d020`

## callees

- `0x180015120`
- `0x180023640`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180015149`
- `MobileNetworking!ReleaseWriteLock` at `0x1800151d6`
- `MobileNetworking!ReleaseWriteLock` at `0x180015149`
- `MobileNetworking!ReleaseWriteLock` at `0x1800151d6`
- `MobileNetworking!AcquireWriteLock` at `0x180015197`
- `MobileNetworking!AcquireWriteLock` at `0x180015197`
- `MobileNetworking!FreeMemory` at `0x1800151f5`
- `MobileNetworking!FreeMemory` at `0x1800151f5`

## pseudocode

```c
__int64 __fastcall PortMgrUnlockAndDeRefPort(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 result; // rax
  __int64 v7; // r9
  _QWORD *v8; // r8
  _QWORD *v9; // [rsp+20h] [rbp-18h] BYREF

  if ( a3 )
    result = ReleaseWriteLock(a1, a1 + 2896, "PortMgrUnlockAndDeRefPort", 694);
  if ( a4 )
  {
    v9 = (_QWORD *)a1;
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      PortMgrDeInitPort(v9);
      AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
      v7 = *v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v8 = (_QWORD *)v9[1], (_QWORD *)*v8 != v9) )
        __fastfail(3u);
      *v8 = v7;
      *(_QWORD *)(v7 + 8) = v8;
      ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
      _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
      return FreeMemory(&v9, "PortMgrDereferencePort", 601);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015120  mov     [rsp+arg_0], rbx
0x180015125  push    rdi
0x180015126  sub     rsp, 30h
0x18001512a  mov     edi, r9d
0x18001512d  mov     rbx, rcx
0x180015130  test    r8d, r8d
0x180015133  jz      short loc_18001514F
0x180015135  lea     rdx, [rcx+0B50h]
0x18001513c  mov     r9d, 2B6h
0x180015142  lea     r8, aPortmgrunlocka; "PortMgrUnlockAndDeRefPort"
0x180015149  call    cs:__imp_ReleaseWriteLock
0x18001514f  test    edi, edi
0x180015151  jnz     short loc_18001515E
0x180015153  mov     rbx, [rsp+38h+arg_0]
0x180015158  add     rsp, 30h
0x18001515c  pop     rdi
0x18001515d  retn
0x18001515e  mov     [rsp+38h+var_18], rbx
0x180015163  mov     eax, 0FFFFFFFFh
0x180015168  lock xadd [rbx+10h], eax
0x18001516d  cmp     eax, 1
0x180015170  jnz     short loc_180015153
0x180015172  mov     rcx, [rsp+38h+var_18]
0x180015177  call    PortMgrDeInitPort
0x18001517c  mov     r9d, 253h
0x180015182  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x180015189  lea     rdx, qword_18003DD98
0x180015190  lea     rcx, g_OneXInfo
0x180015197  call    cs:__imp_AcquireWriteLock
0x18001519d  mov     rax, [rsp+38h+var_18]
0x1800151a2  mov     r9, [rax]
0x1800151a5  cmp     [r9+8], rax
0x1800151a9  jnz     short loc_180015206
0x1800151ab  mov     r8, [rax+8]
0x1800151af  cmp     [r8], rax
0x1800151b2  jnz     short loc_180015206
0x1800151b4  mov     [r8], r9
0x1800151b7  lea     rdx, qword_18003DD98
0x1800151be  mov     [r9+8], r8
0x1800151c2  lea     rcx, g_OneXInfo
0x1800151c9  mov     r9d, 255h
0x1800151cf  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x1800151d6  call    cs:__imp_ReleaseWriteLock
0x1800151dc  lock dec dword ptr cs:qword_18003DD8C+4
0x1800151e3  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x1800151ea  mov     r8d, 259h
0x1800151f0  lea     rcx, [rsp+38h+var_18]
0x1800151f5  call    cs:__imp_FreeMemory
0x1800151fb  mov     rbx, [rsp+38h+arg_0]
0x180015200  add     rsp, 30h
0x180015204  pop     rdi
0x180015205  retn
0x180015206  mov     ecx, 3
0x18001520b  int     29h; Win8: RtlFailFast(ecx)
```
