# ReleaseDataConvert(IDataConvert *)

- ea: `0x1800213b8`
- end: `0x180021453`
- name: `?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z`
- size: `155`
- prototype: `void __fastcall(struct IDataConvert *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b354`
- `0x1800207a0`
- `0x180023fe0`

## callees

- `0x1800213b8`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800213e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800213e7`
- `KERNEL32!LeaveCriticalSection` at `0x18002143b`
- `KERNEL32!LeaveCriticalSection` at `0x18002143b`
- `MSDART!UMSEnterCSWraper` at `0x1800213d5`
- `MSDART!UMSEnterCSWraper` at `0x1800213d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ReleaseDataConvert(struct IDataConvert *a1)
{
  _DWORD *v1; // rbx
  __int64 v3; // rcx

  if ( a1 )
  {
    v1 = g_pcsDataConvert;
    UMSEnterCSWraper(g_pcsDataConvert);
    if ( !v1[3] )
      v1[2] = GetCurrentThreadId();
    ++v1[3];
    ++v1[4];
    if ( !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)g_pIDataConvert + 16LL))(g_pIDataConvert) )
      g_pIDataConvert = 0;
    --v1[4];
    if ( v1[3]-- == 1 )
      v1[2] = -1;
    v3 = *(_QWORD *)v1;
    --*(_DWORD *)(v3 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  }
}

```

## disassembly

```asm
0x1800213b8  test    rcx, rcx
0x1800213bb  jz      locret_180021451
0x1800213c1  mov     [rsp+arg_8], rbx
0x1800213c6  push    rdi
0x1800213c7  sub     rsp, 20h
0x1800213cb  mov     rbx, cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA; CFoxCriticalSection * g_pcsDataConvert
0x1800213d2  mov     rcx, rbx
0x1800213d5  call    cs:__imp_UMSEnterCSWraper
0x1800213dc  nop     dword ptr [rax+rax+00h]
0x1800213e1  cmp     dword ptr [rbx+0Ch], 0
0x1800213e5  jnz     short loc_1800213F6
0x1800213e7  call    cs:__imp_GetCurrentThreadId
0x1800213ee  nop     dword ptr [rax+rax+00h]
0x1800213f3  mov     [rbx+8], eax
0x1800213f6  inc     dword ptr [rbx+0Ch]
0x1800213f9  inc     dword ptr [rbx+10h]
0x1800213fc  mov     [rsp+28h+arg_0], rbx
0x180021401  mov     rcx, cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x180021408  mov     rax, [rcx]
0x18002140b  mov     rax, [rax+10h]
0x18002140f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021414  test    eax, eax
0x180021416  jnz     short loc_180021423
0x180021418  mov     cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA, 0; IDataConvert * g_pIDataConvert
0x180021423  or      ecx, 0FFFFFFFFh
0x180021426  add     [rbx+10h], ecx
0x180021429  add     [rbx+0Ch], ecx
0x18002142c  jnz     short loc_180021431
0x18002142e  mov     [rbx+8], ecx
0x180021431  mov     rcx, [rbx]
0x180021434  dec     dword ptr [rcx+30h]
0x180021437  add     rcx, 8; lpCriticalSection
0x18002143b  call    cs:__imp_LeaveCriticalSection
0x180021442  nop     dword ptr [rax+rax+00h]
0x180021447  mov     rbx, [rsp+28h+arg_8]
0x18002144c  add     rsp, 20h
0x180021450  pop     rdi
0x180021451  retn
```
