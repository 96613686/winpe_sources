# CSharePermissionList::_MergePermission(void *,SHARE_ROLE)

- ea: `0x18000f0c8`
- end: `0x18000f24a`
- name: `?_MergePermission@CSharePermissionList@@AEAAJPEAXW4SHARE_ROLE@@@Z`
- size: `386`
- prototype: `int(CSharePermissionList *__hidden this, void *, enum SHARE_ROLE)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d380`
- `0x18000e8b0`

## callees

- `0x1800098dc`
- `0x18000f0c8`
- `0x18000f7f0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f1bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f1bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f23f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f23f`
- `SHCORE!SHStrDupW` at `0x18000f170`
- `SHCORE!SHStrDupW` at `0x18000f170`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000f148`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000f148`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f0f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f0f3`

## pseudocode

```c
__int64 __fastcall CSharePermissionList::_MergePermission(CSharePermissionList *this, void *a2, enum SHARE_ROLE a3)
{
  HRESULT Error; // ebx
  unsigned int i; // esi
  _DWORD *v7; // rdi
  int v8; // eax
  __int64 (__fastcall *v9)(_DWORD *, _QWORD); // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, _OWORD *); // rax
  __int64 v12; // rbx
  _OWORD v14[2]; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR pszStr2; // [rsp+68h] [rbp+20h] BYREF

  pszStr2 = 0;
  if ( ConvertSidToStringSidW(a2, (LPWSTR *)&pszStr2) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  for ( i = 0; ; ++i )
  {
    v7 = (_DWORD *)*((_QWORD *)this + 2);
    v8 = v7 ? *v7 : 0;
    if ( (int)i >= v8 )
      break;
    v9 = (__int64 (__fastcall *)(_DWORD *, _QWORD))qword_180095A38;
    if ( qword_180095A38 == -1 )
    {
      GetProcFromComCtl32(&qword_180095A38, 323);
      v9 = (__int64 (__fastcall *)(_DWORD *, _QWORD))qword_180095A38;
    }
    if ( v9 )
      v10 = v9(v7, i);
    else
      v10 = 0;
    if ( !StrCmpICW(*(LPCWSTR *)(v10 + 8), pszStr2) )
    {
      if ( *(_DWORD *)v10 < a3 )
        *(_DWORD *)v10 = a3;
      goto LABEL_18;
    }
  }
  v14[0] = 0;
  LODWORD(v14[0]) = a3;
  Error = SHStrDupW(pszStr2, (LPWSTR *)v14 + 1);
  if ( Error < 0 )
    goto LABEL_18;
  v11 = (__int64 (__fastcall *)(__int64, __int64, _OWORD *))qword_180095A48;
  v12 = *((_QWORD *)this + 2);
  if ( qword_180095A48 == -1 )
  {
    GetProcFromComCtl32(&qword_180095A48, 324);
    v11 = (__int64 (__fastcall *)(__int64, __int64, _OWORD *))qword_180095A48;
  }
  if ( v11 )
  {
    Error = v11(v12, 0x7FFFFFFF, v14);
    if ( Error >= 0 )
      goto LABEL_18;
  }
  else
  {
    Error = -1;
  }
  CoTaskMemFree(*((LPVOID *)&v14[0] + 1));
LABEL_18:
  LocalFree((HLOCAL)pszStr2);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000f0c8  mov     r11, rsp
0x18000f0cb  mov     [r11+8], rbx
0x18000f0cf  mov     [r11+10h], rbp
0x18000f0d3  push    rsi
0x18000f0d4  push    rdi
0x18000f0d5  push    r14
0x18000f0d7  sub     rsp, 30h
0x18000f0db  mov     rax, rdx
0x18000f0de  mov     qword ptr [r11+20h], 0
0x18000f0e6  mov     r14, rcx
0x18000f0e9  lea     rdx, [r11+20h]; StringSid
0x18000f0ed  mov     rcx, rax; Sid
0x18000f0f0  mov     ebp, r8d
0x18000f0f3  call    cs:__imp_ConvertSidToStringSidW
0x18000f0f9  test    eax, eax
0x18000f0fb  jz      loc_18000F1DD
0x18000f101  xor     ebx, ebx
0x18000f103  xor     esi, esi
0x18000f105  mov     rdi, [r14+10h]
0x18000f109  test    rdi, rdi
0x18000f10c  jz      loc_18000F1D6
0x18000f112  mov     eax, [rdi]
0x18000f114  cmp     esi, eax
0x18000f116  jge     short loc_18000F15A
0x18000f118  mov     rax, cs:qword_180095A38
0x18000f11f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f123  jz      loc_18000F1F5
0x18000f129  test    rax, rax
0x18000f12c  jz      loc_18000F1EE
0x18000f132  mov     edx, esi
0x18000f134  mov     rcx, rdi
0x18000f137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f13c  mov     rdi, rax
0x18000f13f  mov     rdx, [rsp+48h+pszStr2]; pszStr2
0x18000f144  mov     rcx, [rdi+8]; pszStr1
0x18000f148  call    cs:__imp_StrCmpICW
0x18000f14e  test    eax, eax
0x18000f150  jz      loc_18000F212
0x18000f156  inc     esi
0x18000f158  jmp     short loc_18000F105
0x18000f15a  mov     rcx, [rsp+48h+pszStr2]; psz
0x18000f15f  lea     rdx, [rsp+48h+ppwsz]; ppwsz
0x18000f164  xorps   xmm0, xmm0
0x18000f167  movups  xmmword ptr [rsp+20h], xmm0
0x18000f16c  mov     [rsp+48h+var_28], ebp
0x18000f170  call    cs:__imp_SHStrDupW
0x18000f176  mov     ebx, eax
0x18000f178  test    eax, eax
0x18000f17a  js      short loc_18000F1B6
0x18000f17c  mov     rax, cs:qword_180095A48
0x18000f183  mov     rbx, [r14+10h]
0x18000f187  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f18b  jz      loc_18000F21A
0x18000f191  test    rax, rax
0x18000f194  jz      loc_18000F237
0x18000f19a  lea     r8, [rsp+48h+var_28]
0x18000f19f  mov     edx, 7FFFFFFFh
0x18000f1a4  mov     rcx, rbx
0x18000f1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ac  mov     ebx, eax
0x18000f1ae  test    eax, eax
0x18000f1b0  js      loc_18000F23A
0x18000f1b6  mov     rcx, [rsp+48h+pszStr2]; hMem
0x18000f1bb  call    cs:__imp_LocalFree
0x18000f1c1  mov     rbp, [rsp+48h+arg_8]
0x18000f1c6  mov     eax, ebx
0x18000f1c8  mov     rbx, [rsp+48h+arg_0]
0x18000f1cd  add     rsp, 30h
0x18000f1d1  pop     r14
0x18000f1d3  pop     rdi
0x18000f1d4  pop     rsi
0x18000f1d5  retn
0x18000f1d6  xor     eax, eax
0x18000f1d8  jmp     loc_18000F114
0x18000f1dd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f1e2  mov     ebx, eax
0x18000f1e4  test    eax, eax
0x18000f1e6  jns     loc_18000F103
0x18000f1ec  jmp     short loc_18000F1C1
0x18000f1ee  xor     edi, edi
0x18000f1f0  jmp     loc_18000F13F
0x18000f1f5  mov     edx, 143h
0x18000f1fa  lea     rcx, qword_180095A38
0x18000f201  call    _GetProcFromComCtl32
0x18000f206  mov     rax, cs:qword_180095A38
0x18000f20d  jmp     loc_18000F129
0x18000f212  cmp     [rdi], ebp
0x18000f214  jge     short loc_18000F1B6
0x18000f216  mov     [rdi], ebp
0x18000f218  jmp     short loc_18000F1B6
0x18000f21a  mov     edx, 144h
0x18000f21f  lea     rcx, qword_180095A48
0x18000f226  call    _GetProcFromComCtl32
0x18000f22b  mov     rax, cs:qword_180095A48
0x18000f232  jmp     loc_18000F191
0x18000f237  or      ebx, 0FFFFFFFFh
0x18000f23a  mov     rcx, [rsp+48h+ppwsz]; pv
0x18000f23f  call    cs:__imp_CoTaskMemFree
0x18000f245  jmp     loc_18000F1B6
```
