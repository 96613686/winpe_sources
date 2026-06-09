# CHidPairingPlugin::GetAccessoryImgPaths(ushort * *,ushort * *,ushort * *)

- ea: `0x180024b30`
- end: `0x180024bd8`
- name: `?GetAccessoryImgPaths@CHidPairingPlugin@@UEAAJPEAPEAG00@Z`
- size: `168`
- prototype: `int(CHidPairingPlugin *__hidden this, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180024b30`
- `0x180026670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bbe`

## pseudocode

```c
__int64 __fastcall CHidPairingPlugin::GetAccessoryImgPaths(
        const unsigned __int16 **this,
        unsigned __int16 **a2,
        LPVOID *a3,
        LPVOID *a4)
{
  CHidPairingPlugin *v8; // rcx
  int v9; // ebx
  CHidPairingPlugin *v10; // rcx

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v9 = CHidPairingPlugin::_ProvideString((CHidPairingPlugin *)this, this[57], a2);
  if ( v9 < 0
    || (v9 = CHidPairingPlugin::_ProvideString(v8, this[63], (unsigned __int16 **)a3), v9 < 0)
    || (v9 = CHidPairingPlugin::_ProvideString(v10, this[69], (unsigned __int16 **)a4), v9 < 0) )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
    CoTaskMemFree(*a3);
    *a3 = 0;
    CoTaskMemFree(*a4);
    *a4 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180024b30  push    rbx
0x180024b32  push    rbp
0x180024b33  push    rsi
0x180024b34  push    rdi
0x180024b35  push    r14
0x180024b37  sub     rsp, 20h
0x180024b3b  mov     qword ptr [rdx], 0
0x180024b42  mov     rsi, r8
0x180024b45  mov     qword ptr [r8], 0
0x180024b4c  mov     r14, rdx
0x180024b4f  mov     qword ptr [r9], 0
0x180024b56  mov     r8, rdx; unsigned __int16 **
0x180024b59  mov     rdx, [rcx+1C8h]; unsigned __int16 *
0x180024b60  mov     rdi, r9
0x180024b63  mov     rbp, rcx
0x180024b66  call    ?_ProvideString@CHidPairingPlugin@@AEAAJPEBGPEAPEAG@Z; CHidPairingPlugin::_ProvideString(ushort const *,ushort * *)
0x180024b6b  mov     ebx, eax
0x180024b6d  test    eax, eax
0x180024b6f  js      short loc_180024B9B
0x180024b71  mov     rdx, [rbp+1F8h]; unsigned __int16 *
0x180024b78  mov     r8, rsi; unsigned __int16 **
0x180024b7b  call    ?_ProvideString@CHidPairingPlugin@@AEAAJPEBGPEAPEAG@Z; CHidPairingPlugin::_ProvideString(ushort const *,ushort * *)
0x180024b80  mov     ebx, eax
0x180024b82  test    eax, eax
0x180024b84  js      short loc_180024B9B
0x180024b86  mov     rdx, [rbp+228h]; unsigned __int16 *
0x180024b8d  mov     r8, rdi; unsigned __int16 **
0x180024b90  call    ?_ProvideString@CHidPairingPlugin@@AEAAJPEBGPEAPEAG@Z; CHidPairingPlugin::_ProvideString(ushort const *,ushort * *)
0x180024b95  mov     ebx, eax
0x180024b97  test    eax, eax
0x180024b99  jns     short loc_180024BCB
0x180024b9b  mov     rcx, [r14]; pv
0x180024b9e  call    cs:__imp_CoTaskMemFree
0x180024ba4  mov     qword ptr [r14], 0
0x180024bab  mov     rcx, [rsi]; pv
0x180024bae  call    cs:__imp_CoTaskMemFree
0x180024bb4  mov     qword ptr [rsi], 0
0x180024bbb  mov     rcx, [rdi]; pv
0x180024bbe  call    cs:__imp_CoTaskMemFree
0x180024bc4  mov     qword ptr [rdi], 0
0x180024bcb  mov     eax, ebx
0x180024bcd  add     rsp, 20h
0x180024bd1  pop     r14
0x180024bd3  pop     rdi
0x180024bd4  pop     rsi
0x180024bd5  pop     rbp
0x180024bd6  pop     rbx
0x180024bd7  retn
```
