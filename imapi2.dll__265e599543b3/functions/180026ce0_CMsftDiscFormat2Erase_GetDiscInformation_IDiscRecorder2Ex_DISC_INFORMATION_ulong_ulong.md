# CMsftDiscFormat2Erase::GetDiscInformation(IDiscRecorder2Ex *,_DISC_INFORMATION * *,ulong *,ulong)

- ea: `0x180026ce0`
- end: `0x180026d9f`
- name: `?GetDiscInformation@CMsftDiscFormat2Erase@@CAJPEAUIDiscRecorder2Ex@@PEAPEAU_DISC_INFORMATION@@PEAKK@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct IDiscRecorder2Ex *, struct _DISC_INFORMATION **, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180025508`
- `0x180026ff0`

## callees

- `0x180014134`
- `0x180026ce0`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180026d73`
- `ole32!CoTaskMemFree` at `0x180026d73`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Erase::GetDiscInformation(struct IDiscRecorder2Ex *a1, LPVOID *a2, unsigned int *a3)
{
  int v5; // esi

  if ( !a2 || !a3 )
    return 2147500035LL;
  v5 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *))a1->lpVtbl->GetDiscInformation)(a1);
  if ( v5 >= 0 && *a3 < 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 33, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, 4, *a3);
    }
    v5 = -2136340222;
    if ( *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    *a3 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026ce0  mov     [rsp+arg_0], rbx
0x180026ce5  mov     [rsp+arg_8], rsi
0x180026cea  push    rdi
0x180026ceb  sub     rsp, 30h
0x180026cef  mov     rbx, r8
0x180026cf2  mov     rdi, rdx
0x180026cf5  test    rdx, rdx
0x180026cf8  jz      loc_180026D8A
0x180026cfe  test    rbx, rbx
0x180026d01  jz      loc_180026D8A
0x180026d07  mov     rax, [rcx]
0x180026d0a  mov     rax, [rax+50h]
0x180026d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d13  mov     esi, eax
0x180026d15  test    eax, eax
0x180026d17  js      short loc_180026D86
0x180026d19  mov     eax, [rbx]
0x180026d1b  mov     r9d, 4
0x180026d21  cmp     eax, r9d
0x180026d24  jnb     short loc_180026D86
0x180026d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d2d  lea     rdx, WPP_GLOBAL_Control
0x180026d34  cmp     rcx, rdx
0x180026d37  jz      short loc_180026D66
0x180026d39  test    [rcx+10Ch], r9b
0x180026d40  jz      short loc_180026D66
0x180026d42  cmp     byte ptr [rcx+109h], 3
0x180026d49  jb      short loc_180026D66
0x180026d4b  mov     rcx, [rcx+100h]
0x180026d52  lea     edx, [r9+1Dh]
0x180026d56  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x180026d5d  mov     [rsp+38h+var_18], eax
0x180026d61  call    WPP_SF_Dd
0x180026d66  mov     rcx, [rdi]; pv
0x180026d69  mov     esi, 80AA0902h
0x180026d6e  test    rcx, rcx
0x180026d71  jz      short loc_180026D80
0x180026d73  call    cs:__imp_CoTaskMemFree
0x180026d79  mov     qword ptr [rdi], 0
0x180026d80  mov     dword ptr [rbx], 0
0x180026d86  mov     eax, esi
0x180026d88  jmp     short loc_180026D8F
0x180026d8a  mov     eax, 80004003h
0x180026d8f  mov     rbx, [rsp+38h+arg_0]
0x180026d94  mov     rsi, [rsp+38h+arg_8]
0x180026d99  add     rsp, 30h
0x180026d9d  pop     rdi
0x180026d9e  retn
```
