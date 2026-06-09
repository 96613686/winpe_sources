# s_ItemCompare(IOOBEItem *,IOOBEItem *,__int64)

- ea: `0x18001a700`
- end: `0x18001a797`
- name: `?s_ItemCompare@@YAHPEAUIOOBEItem@@0_J@Z`
- size: `151`
- prototype: `int __stdcall(void *p1, void *p2, LPARAM lParam)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a7a0`

## callees

- `0x18001a700`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001a76b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001a76b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a783`

## pseudocode

```c
__int64 __fastcall s_ItemCompare(__int64 *p1, void *p2, LPARAM lParam)
{
  __int64 v3; // rax
  int v5; // ebx
  PCNZWCH lpString2; // [rsp+40h] [rbp+8h] BYREF
  PCNZWCH lpString1; // [rsp+58h] [rbp+20h] BYREF

  v3 = *p1;
  lpString1 = 0;
  v5 = -1;
  lpString2 = 0;
  if ( (*(int (__fastcall **)(__int64 *, PCNZWCH *, LPARAM))(v3 + 24))(p1, &lpString1, lParam) >= 0 )
  {
    if ( (*(int (__fastcall **)(void *, PCNZWCH *))(*(_QWORD *)p2 + 24LL))(p2, &lpString2) >= 0 )
    {
      v5 = CompareStringW(0x400u, 0, lpString1, -1, lpString2, -1);
      CoTaskMemFree((LPVOID)lpString2);
    }
    CoTaskMemFree((LPVOID)lpString1);
  }
  return (unsigned int)(v5 - 2);
}

```

## disassembly

```asm
0x18001a700  mov     r11, rsp
0x18001a703  mov     [r11+10h], rbx
0x18001a707  push    rdi
0x18001a708  sub     rsp, 30h
0x18001a70c  mov     rax, [rcx]
0x18001a70f  mov     rdi, rdx
0x18001a712  lea     rdx, [r11+20h]
0x18001a716  mov     qword ptr [r11+20h], 0
0x18001a71e  or      ebx, 0FFFFFFFFh
0x18001a721  mov     qword ptr [r11+8], 0
0x18001a729  mov     rax, [rax+18h]
0x18001a72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a732  test    eax, eax
0x18001a734  js      short loc_18001A789
0x18001a736  mov     rax, [rdi]
0x18001a739  lea     rdx, [rsp+38h+arg_0]
0x18001a73e  mov     rcx, rdi
0x18001a741  mov     rax, [rax+18h]
0x18001a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a74a  test    eax, eax
0x18001a74c  js      short loc_18001A77E
0x18001a74e  mov     rax, [rsp+38h+arg_0]
0x18001a753  mov     r9d, ebx; cchCount1
0x18001a756  mov     r8, [rsp+38h+lpString1]; lpString1
0x18001a75b  xor     edx, edx; dwCmpFlags
0x18001a75d  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18001a761  mov     ecx, 400h; Locale
0x18001a766  mov     [rsp+38h+lpString2], rax; lpString2
0x18001a76b  call    cs:__imp_CompareStringW
0x18001a771  mov     rcx, [rsp+38h+arg_0]; pv
0x18001a776  mov     ebx, eax
0x18001a778  call    cs:__imp_CoTaskMemFree
0x18001a77e  mov     rcx, [rsp+38h+lpString1]; pv
0x18001a783  call    cs:__imp_CoTaskMemFree
0x18001a789  lea     eax, [rbx-2]
0x18001a78c  mov     rbx, [rsp+38h+arg_8]
0x18001a791  add     rsp, 30h
0x18001a795  pop     rdi
0x18001a796  retn
```
