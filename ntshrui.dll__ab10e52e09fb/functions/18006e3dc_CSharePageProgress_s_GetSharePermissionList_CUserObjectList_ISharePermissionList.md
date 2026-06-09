# CSharePageProgress::_s_GetSharePermissionList(CUserObjectList *,ISharePermissionList * *)

- ea: `0x18006e3dc`
- end: `0x18006e4c9`
- name: `?_s_GetSharePermissionList@CSharePageProgress@@CAJPEAVCUserObjectList@@PEAPEAUISharePermissionList@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct CUserObjectList *this, struct ISharePermissionList **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006e6f4`

## callees

- `0x1800098dc`
- `0x18006e3dc`
- `0x1800707b0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e473`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e414`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e414`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e43d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e43d`

## pseudocode

```c
__int64 __fastcall CSharePageProgress::_s_GetSharePermissionList(unsigned int **this, struct ISharePermissionList **a2)
{
  HRESULT Error; // ebx
  unsigned int *Next; // rdi
  void *v6; // rcx
  LPVOID v8; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  Error = CoCreateInstance(&CLSID_SharePermissionList, 0, 1u, &GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa, &v8);
  if ( Error >= 0 )
  {
    Next = *this;
    while ( Next )
    {
      v6 = *(void **)Next;
      StringSid = 0;
      if ( ConvertSidToStringSidW(v6, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        Error = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, _QWORD))(*(_QWORD *)v8 + 56LL))(v8, StringSid, Next[12]);
        LocalFree(StringSid);
      }
      Next = (unsigned int *)CUserObjectList::GetNext((CUserObjectList *)this, (struct CUserObject *)Next);
      if ( Error < 0 )
        goto LABEL_10;
    }
    Error = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ISharePermissionList **))v8)(
              v8,
              &GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa,
              a2);
LABEL_10:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006e3dc  mov     r11, rsp
0x18006e3df  mov     [r11+8], rbx
0x18006e3e3  push    rbp
0x18006e3e4  push    rsi
0x18006e3e5  push    rdi
0x18006e3e6  sub     rsp, 30h
0x18006e3ea  mov     rbp, rdx
0x18006e3ed  mov     qword ptr [r11+18h], 0
0x18006e3f5  xor     edx, edx; pUnkOuter
0x18006e3f7  lea     rax, [r11+18h]
0x18006e3fb  mov     rsi, rcx
0x18006e3fe  mov     [r11-28h], rax
0x18006e402  lea     r9, _GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa; riid
0x18006e409  lea     rcx, CLSID_SharePermissionList; rclsid
0x18006e410  lea     r8d, [rdx+1]; dwClsContext
0x18006e414  call    cs:__imp_CoCreateInstance
0x18006e41a  mov     ebx, eax
0x18006e41c  test    eax, eax
0x18006e41e  js      loc_18006E4BA
0x18006e424  mov     rdi, [rsi]
0x18006e427  test    rdi, rdi
0x18006e42a  jz      short loc_18006E48D
0x18006e42c  mov     rcx, [rdi]; Sid
0x18006e42f  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18006e434  mov     [rsp+48h+StringSid], 0
0x18006e43d  call    cs:__imp_ConvertSidToStringSidW
0x18006e443  test    eax, eax
0x18006e445  jnz     short loc_18006E452
0x18006e447  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006e44c  mov     ebx, eax
0x18006e44e  test    eax, eax
0x18006e450  js      short loc_18006E479
0x18006e452  mov     rcx, [rsp+48h+arg_10]
0x18006e457  mov     r8d, [rdi+30h]
0x18006e45b  mov     rdx, [rsp+48h+StringSid]
0x18006e460  mov     rax, [rcx]
0x18006e463  mov     rax, [rax+38h]
0x18006e467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e46c  mov     rcx, [rsp+48h+StringSid]; hMem
0x18006e471  mov     ebx, eax
0x18006e473  call    cs:__imp_LocalFree
0x18006e479  mov     rdx, rdi; struct CUserObject *
0x18006e47c  mov     rcx, rsi; this
0x18006e47f  call    ?GetNext@CUserObjectList@@QEAAPEAVCUserObject@@PEAV2@@Z; CUserObjectList::GetNext(CUserObject *)
0x18006e484  mov     rdi, rax
0x18006e487  test    ebx, ebx
0x18006e489  jns     short loc_18006E427
0x18006e48b  jmp     short loc_18006E4A9
0x18006e48d  mov     rcx, [rsp+48h+arg_10]
0x18006e492  lea     rdx, _GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa
0x18006e499  mov     r8, rbp
0x18006e49c  mov     rax, [rcx]
0x18006e49f  mov     rax, [rax]
0x18006e4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4a7  mov     ebx, eax
0x18006e4a9  mov     rcx, [rsp+48h+arg_10]
0x18006e4ae  mov     rax, [rcx]
0x18006e4b1  mov     rax, [rax+10h]
0x18006e4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4ba  mov     eax, ebx
0x18006e4bc  mov     rbx, [rsp+48h+arg_0]
0x18006e4c1  add     rsp, 30h
0x18006e4c5  pop     rdi
0x18006e4c6  pop     rsi
0x18006e4c7  pop     rbp
0x18006e4c8  retn
```
