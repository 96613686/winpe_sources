# std::_Construct_in_place<ToastHelper,_GUID const &>(ToastHelper &,_GUID const &)

- ea: `0x180016a68`
- end: `0x180016aa2`
- name: `??$_Construct_in_place@VToastHelper@@AEBU_GUID@@@std@@YAXAEAVToastHelper@@AEBU_GUID@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180016aa8`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180016a93`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180016a93`

## pseudocode

```c
__int64 __fastcall std::_Construct_in_place<ToastHelper,_GUID const &>(__int64 a1, _OWORD *a2)
{
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = *a2;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  return (unsigned int)_InterlockedExchange((volatile __int32 *)(a1 + 32), SHTaskPoolGetUniqueContext());
}

```

## disassembly

```asm
0x180016a68  push    rbx
0x180016a6a  sub     rsp, 20h
0x180016a6e  mov     rbx, rcx
0x180016a71  xor     eax, eax
0x180016a73  xor     ecx, ecx
0x180016a75  mov     [rbx], rcx
0x180016a78  mov     [rbx+8], rcx
0x180016a7c  movups  xmm0, xmmword ptr [rdx]
0x180016a7f  movdqu  xmmword ptr [rbx+10h], xmm0
0x180016a84  mov     [rbx+20h], eax
0x180016a87  mov     [rbx+28h], rcx
0x180016a8b  mov     [rbx+30h], rcx
0x180016a8f  mov     [rbx+38h], rcx
0x180016a93  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180016a99  xchg    eax, [rbx+20h]
0x180016a9c  add     rsp, 20h
0x180016aa0  pop     rbx
0x180016aa1  retn
```
