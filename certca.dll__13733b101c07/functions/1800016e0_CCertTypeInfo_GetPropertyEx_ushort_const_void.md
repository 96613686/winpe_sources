# CCertTypeInfo::GetPropertyEx(ushort const *,void *)

- ea: `0x1800016e0`
- end: `0x180001918`
- name: `?GetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX@Z`
- size: `568`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, const unsigned __int16 *, HLOCAL *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800315b4`
- `0x180033f70`

## callees

- `0x1800016e0`
- `0x180001920`
- `0x180002ef0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001743`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000179e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800017da`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001828`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001864`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800018b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001743`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000179e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800017da`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001828`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001864`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800018b2`

## string_xrefs

- `0x18000171c`: `msPKI-Template-Schema-Version`
- `0x18000183d`: `msPKI-Template-Schema-Version`
- `0x180001770`: `msPKI-Template-Minor-Revision`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::GetPropertyEx(CCertTypeInfo *this, const unsigned __int16 *a2, HLOCAL *a3)
{
  unsigned int v7; // ebp

  if ( !a2 || !a3 )
    return 2147500035LL;
  if ( *((_DWORD *)this + 22) || !(unsigned int)IsV2Property(a2) )
  {
    v7 = 0;
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Template-Minor-Revision", -1) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)this + 16);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-RA-Signature", -1) == 2 )
      {
        *(_DWORD *)a3 = *((_DWORD *)this + 21);
        return 0;
      }
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Minimal-Key-Size", -1) == 2 )
      {
        *(_DWORD *)a3 = *((_DWORD *)this + 20);
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Template-Schema-Version", -1) == 2 )
        {
          *(_DWORD *)a3 = *((_DWORD *)this + 22);
          return 0;
        }
        if ( CompareStringW(0x7Fu, 1u, a2, -1, L"revision", -1) == 2 )
        {
          *(_DWORD *)a3 = *((_DWORD *)this + 36);
          return 0;
        }
        return CCertTypeInfo::GetProperty(this, a2, a3);
      }
    }
    return v7;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Template-Schema-Version", -1) == 2 )
  {
    *(_DWORD *)a3 = 1;
    return 0;
  }
  else
  {
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x1800016e0  mov     [rsp+arg_8], rbx
0x1800016e5  mov     [rsp+arg_10], rsi
0x1800016ea  push    rdi
0x1800016eb  sub     rsp, 30h
0x1800016ef  mov     rdi, r8
0x1800016f2  mov     rbx, rdx
0x1800016f5  mov     rsi, rcx
0x1800016f8  test    rdx, rdx
0x1800016fb  jz      loc_180001903
0x180001701  test    r8, r8
0x180001704  jz      loc_180001903
0x18000170a  cmp     dword ptr [rcx+58h], 0
0x18000170e  jnz     short loc_180001770
0x180001710  mov     rcx, rdx; lpString1
0x180001713  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180001718  test    eax, eax
0x18000171a  jz      short loc_180001770
0x18000171c  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001723  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000172b  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001731  mov     [rsp+38h+lpString2], rax; lpString2
0x180001736  mov     r8, rbx; lpString1
0x180001739  mov     edx, 1; dwCmpFlags
0x18000173e  mov     ecx, 7Fh; Locale
0x180001743  call    cs:__imp_CompareStringW
0x180001749  cmp     eax, 2
0x18000174c  jnz     short loc_180001766
0x18000174e  mov     dword ptr [rdi], 1
0x180001754  xor     eax, eax
0x180001756  mov     rbx, [rsp+38h+arg_8]
0x18000175b  mov     rsi, [rsp+38h+arg_10]
0x180001760  add     rsp, 30h
0x180001764  pop     rdi
0x180001765  retn
0x180001766  mov     eax, 80070490h
0x18000176b  jmp     loc_180001908
0x180001770  lea     rax, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180001777  mov     [rsp+38h+arg_0], rbp
0x18000177c  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001784  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000178a  mov     r8, rbx; lpString1
0x18000178d  mov     [rsp+38h+lpString2], rax; lpString2
0x180001792  mov     edx, 1; dwCmpFlags
0x180001797  mov     ecx, 7Fh; Locale
0x18000179c  xor     ebp, ebp
0x18000179e  call    cs:__imp_CompareStringW
0x1800017a4  cmp     eax, 2
0x1800017a7  jnz     short loc_1800017B3
0x1800017a9  mov     eax, [rsi+40h]
0x1800017ac  mov     [rdi], eax
0x1800017ae  jmp     loc_1800018EC
0x1800017b3  lea     rax, aMspkiRaSignatu; "msPKI-RA-Signature"
0x1800017ba  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800017c2  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800017c8  mov     [rsp+38h+lpString2], rax; lpString2
0x1800017cd  mov     r8, rbx; lpString1
0x1800017d0  mov     edx, 1; dwCmpFlags
0x1800017d5  mov     ecx, 7Fh; Locale
0x1800017da  call    cs:__imp_CompareStringW
0x1800017e0  cmp     eax, 2
0x1800017e3  jnz     short loc_180001801
0x1800017e5  mov     eax, [rsi+54h]
0x1800017e8  mov     [rdi], eax
0x1800017ea  mov     eax, ebp
0x1800017ec  mov     rbp, [rsp+38h+arg_0]
0x1800017f1  mov     rbx, [rsp+38h+arg_8]
0x1800017f6  mov     rsi, [rsp+38h+arg_10]
0x1800017fb  add     rsp, 30h
0x1800017ff  pop     rdi
0x180001800  retn
0x180001801  lea     rax, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180001808  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001810  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001816  mov     [rsp+38h+lpString2], rax; lpString2
0x18000181b  mov     r8, rbx; lpString1
0x18000181e  mov     edx, 1; dwCmpFlags
0x180001823  mov     ecx, 7Fh; Locale
0x180001828  call    cs:__imp_CompareStringW
0x18000182e  cmp     eax, 2
0x180001831  jnz     short loc_18000183D
0x180001833  mov     eax, [rsi+50h]
0x180001836  mov     [rdi], eax
0x180001838  jmp     loc_1800018EC
0x18000183d  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001844  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000184c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001852  mov     [rsp+38h+lpString2], rax; lpString2
0x180001857  mov     r8, rbx; lpString1
0x18000185a  mov     edx, 1; dwCmpFlags
0x18000185f  mov     ecx, 7Fh; Locale
0x180001864  call    cs:__imp_CompareStringW
0x18000186a  cmp     eax, 2
0x18000186d  jnz     short loc_18000188B
0x18000186f  mov     eax, [rsi+58h]
0x180001872  mov     [rdi], eax
0x180001874  mov     eax, ebp
0x180001876  mov     rbp, [rsp+38h+arg_0]
0x18000187b  mov     rbx, [rsp+38h+arg_8]
0x180001880  mov     rsi, [rsp+38h+arg_10]
0x180001885  add     rsp, 30h
0x180001889  pop     rdi
0x18000188a  retn
0x18000188b  lea     rax, aRevision_0; "revision"
0x180001892  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000189a  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800018a0  mov     [rsp+38h+lpString2], rax; lpString2
0x1800018a5  mov     r8, rbx; lpString1
0x1800018a8  mov     edx, 1; dwCmpFlags
0x1800018ad  mov     ecx, 7Fh; Locale
0x1800018b2  call    cs:__imp_CompareStringW
0x1800018b8  cmp     eax, 2
0x1800018bb  jnz     short loc_1800018DC
0x1800018bd  mov     eax, [rsi+90h]
0x1800018c3  mov     [rdi], eax
0x1800018c5  mov     eax, ebp
0x1800018c7  mov     rbp, [rsp+38h+arg_0]
0x1800018cc  mov     rbx, [rsp+38h+arg_8]
0x1800018d1  mov     rsi, [rsp+38h+arg_10]
0x1800018d6  add     rsp, 30h
0x1800018da  pop     rdi
0x1800018db  retn
0x1800018dc  mov     r8, rdi; unsigned __int16 ***
0x1800018df  mov     rdx, rbx; unsigned __int16 *
0x1800018e2  mov     rcx, rsi; this
0x1800018e5  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x1800018ea  mov     ebp, eax
0x1800018ec  mov     eax, ebp
0x1800018ee  mov     rbp, [rsp+38h+arg_0]
0x1800018f3  mov     rbx, [rsp+38h+arg_8]
0x1800018f8  mov     rsi, [rsp+38h+arg_10]
0x1800018fd  add     rsp, 30h
0x180001901  pop     rdi
0x180001902  retn
0x180001903  mov     eax, 80004003h
0x180001908  mov     rbx, [rsp+38h+arg_8]
0x18000190d  mov     rsi, [rsp+38h+arg_10]
0x180001912  add     rsp, 30h
0x180001916  pop     rdi
0x180001917  retn
```
