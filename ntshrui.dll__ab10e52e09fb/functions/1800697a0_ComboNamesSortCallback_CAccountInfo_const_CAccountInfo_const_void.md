# ComboNamesSortCallback(CAccountInfo const *,CAccountInfo const *,void *)

- ea: `0x1800697a0`
- end: `0x18006982a`
- name: `?ComboNamesSortCallback@@YAHPEBVCAccountInfo@@0PEAX@Z`
- size: `138`
- prototype: `int __stdcall(void *p1, void *p2, LPARAM lParam)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800697a0`
- `0x18006aef4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800697e1`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800697e1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800697fe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800697fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006980c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006980c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069817`

## pseudocode

```c
__int64 __fastcall ComboNamesSortCallback(const struct CAccountInfo *p1, const struct CAccountInfo *p2, LPARAM lParam)
{
  unsigned int v4; // ebx
  const WCHAR *lpString2; // rbx
  const WCHAR *v6; // rdi
  LCID UserDefaultLCID; // eax
  PCNZWCH lpString1; // [rsp+30h] [rbp-18h] BYREF
  PCNZWCH v10; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  lpString1 = 0;
  v10 = 0;
  if ( _GetComboName(p1, (unsigned __int16 **)&lpString1) >= 0 )
  {
    if ( _GetComboName(p2, (unsigned __int16 **)&v10) >= 0 )
    {
      lpString2 = v10;
      v6 = lpString1;
      UserDefaultLCID = GetUserDefaultLCID();
      v4 = CompareStringW(UserDefaultLCID, 1u, v6, -1, lpString2, -1) - 2;
      CoTaskMemFree((LPVOID)v10);
    }
    CoTaskMemFree((LPVOID)lpString1);
  }
  return v4;
}

```

## disassembly

```asm
0x1800697a0  mov     rax, rsp
0x1800697a3  mov     [rax+8], rbx
0x1800697a7  push    rdi
0x1800697a8  sub     rsp, 40h
0x1800697ac  mov     rdi, rdx
0x1800697af  xor     ebx, ebx
0x1800697b1  lea     rdx, [rax-18h]; unsigned __int16 **
0x1800697b5  mov     [rax-18h], rbx
0x1800697b9  mov     [rax+20h], rbx
0x1800697bd  call    ?_GetComboName@@YAJPEBVCAccountInfo@@PEAPEAG@Z; _GetComboName(CAccountInfo const *,ushort * *)
0x1800697c2  test    eax, eax
0x1800697c4  js      short loc_18006981D
0x1800697c6  lea     rdx, [rsp+48h+arg_18]; unsigned __int16 **
0x1800697cb  mov     rcx, rdi; struct CAccountInfo *
0x1800697ce  call    ?_GetComboName@@YAJPEBVCAccountInfo@@PEAPEAG@Z; _GetComboName(CAccountInfo const *,ushort * *)
0x1800697d3  test    eax, eax
0x1800697d5  js      short loc_180069812
0x1800697d7  mov     rbx, [rsp+48h+arg_18]
0x1800697dc  mov     rdi, [rsp+48h+lpString1]
0x1800697e1  call    cs:__imp_GetUserDefaultLCID
0x1800697e7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800697eb  mov     r8, rdi; lpString1
0x1800697ee  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x1800697f3  mov     ecx, eax; Locale
0x1800697f5  mov     [rsp+48h+lpString2], rbx; lpString2
0x1800697fa  lea     edx, [r9+2]; dwCmpFlags
0x1800697fe  call    cs:__imp_CompareStringW
0x180069804  mov     rcx, [rsp+48h+arg_18]; pv
0x180069809  lea     ebx, [rax-2]
0x18006980c  call    cs:__imp_CoTaskMemFree
0x180069812  mov     rcx, [rsp+48h+lpString1]; pv
0x180069817  call    cs:__imp_CoTaskMemFree
0x18006981d  mov     eax, ebx
0x18006981f  mov     rbx, [rsp+48h+arg_0]
0x180069824  add     rsp, 40h
0x180069828  pop     rdi
0x180069829  retn
```
