# EapLm::IEapMethod::ConstructMethodRegPath(_EAP_METHOD_TYPE const &,wchar_t const * const,wchar_t *,ulong)

- ea: `0x18002e67c`
- end: `0x18002e6e5`
- name: `?ConstructMethodRegPath@IEapMethod@EapLm@@SAJAEBU_EAP_METHOD_TYPE@@QEB_WPEA_WK@Z`
- size: `105`
- prototype: `__int64 __fastcall(const struct _EAP_METHOD_TYPE *, const wchar_t *const, wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001b378`
- `0x180029820`

## callees

- `0x1800034ec`
- `0x18002e67c`

## string_xrefs

- `0x18002e683`: `System\CurrentControlSet\Services\EapHost\Methods`

## pseudocode

```c
__int64 __fastcall EapLm::IEapMethod::ConstructMethodRegPath(
        const struct _EAP_METHOD_TYPE *a1,
        const wchar_t *const a2,
        wchar_t *a3)
{
  int type; // edx

  type = a1->eapType.type;
  if ( (_BYTE)type == 0xFE )
    return StringCchPrintfW(
             a3,
             0x104u,
             L"%s\\%d\\%d\\%d\\%d",
             L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
             a1->dwAuthorId,
             type,
             a1->eapType.dwVendorId,
             a1->eapType.dwVendorType);
  else
    return StringCchPrintfW(
             a3,
             0x104u,
             L"%s\\%d\\%d",
             L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
             a1->dwAuthorId,
             a1->eapType.type);
}

```

## disassembly

```asm
0x18002e67c  sub     rsp, 48h
0x18002e680  movzx   edx, byte ptr [rcx]
0x18002e683  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ea"...
0x18002e68a  mov     r10, r8
0x18002e68d  cmp     dl, 0FEh
0x18002e690  jnz     short loc_18002E6C1
0x18002e692  mov     eax, [rcx+8]
0x18002e695  lea     r8, aSDDDD; "%s\\%d\\%d\\%d\\%d"
0x18002e69c  mov     [rsp+48h+var_10], eax
0x18002e6a0  mov     eax, [rcx+4]
0x18002e6a3  mov     [rsp+48h+var_18], eax
0x18002e6a7  mov     eax, [rcx+0Ch]
0x18002e6aa  mov     rcx, r10; wchar_t *
0x18002e6ad  mov     [rsp+48h+var_20], edx
0x18002e6b1  mov     edx, 104h; unsigned __int64
0x18002e6b6  mov     [rsp+48h+var_28], eax
0x18002e6ba  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002e6bf  jmp     short loc_18002E6E0
0x18002e6c1  mov     eax, [rcx+0Ch]
0x18002e6c4  lea     r8, aSDD; "%s\\%d\\%d"
0x18002e6cb  mov     [rsp+48h+var_20], edx
0x18002e6cf  mov     rcx, r10; wchar_t *
0x18002e6d2  mov     edx, 104h; unsigned __int64
0x18002e6d7  mov     [rsp+48h+var_28], eax
0x18002e6db  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002e6e0  add     rsp, 48h
0x18002e6e4  retn
```
