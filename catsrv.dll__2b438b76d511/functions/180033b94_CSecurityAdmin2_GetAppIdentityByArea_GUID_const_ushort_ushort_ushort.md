# CSecurityAdmin2::GetAppIdentityByArea(_GUID const &,ushort *,ushort * *,ushort * *)

- ea: `0x180033b94`
- end: `0x180033cb2`
- name: `?GetAppIdentityByArea@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAGPEAPEAG2@Z`
- size: `286`
- prototype: `int(CSecurityAdmin2 *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033b70`
- `0x180033cc0`

## callees

- `0x18000b6a0`
- `0x18001a6c8`
- `0x180033b94`
- `0x1800345c8`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033c38`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180033be9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180033be9`

## pseudocode

```c
int __fastcall CSecurityAdmin2::GetAppIdentityByArea(
        CSecurityAdmin2 *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  int result; // eax
  unsigned __int16 *v7; // rbx
  SIZE_T v8; // rdi
  unsigned __int16 *v9; // rax
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  int v12; // edi
  size_t Size; // [rsp+20h] [rbp-88h] BYREF
  void *pv; // [rsp+28h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-78h] BYREF

  *a4 = 0;
  pv = 0;
  LODWORD(Size) = 0;
  *a5 = 0;
  result = StringFromGUID2(a2, sz, 40);
  if ( result >= 0 )
  {
    result = RetrievePrivateData(a3, sz, (unsigned __int16 **)&pv, (unsigned int *)&Size);
    if ( result == -2147024894 )
    {
      return 1;
    }
    else if ( result >= 0 )
    {
      v7 = (unsigned __int16 *)pv;
      v8 = 2 * (unsigned int)safe_lstrlenW((const unsigned __int16 *)pv) + 2;
      v9 = (unsigned __int16 *)CoTaskMemAlloc(v8);
      *a5 = v9;
      if ( v9 )
      {
        v12 = StringCbCopyW(v9, v8, v7);
        memset_0(v7, 0, (unsigned int)Size);
      }
      else
      {
        CoTaskMemFree(0);
        v10 = (unsigned int)Size;
        v11 = v7;
        if ( (_DWORD)Size )
        {
          do
          {
            *(_BYTE *)v11 = 0;
            v11 = (unsigned __int16 *)((char *)v11 + 1);
            --v10;
          }
          while ( v10 );
        }
        v12 = -2147024882;
      }
      CoTaskMemFree(v7);
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180033b94  push    rbx
0x180033b96  push    rsi
0x180033b97  push    rdi
0x180033b98  sub     rsp, 90h
0x180033b9f  mov     rax, cs:__security_cookie
0x180033ba6  xor     rax, rsp
0x180033ba9  mov     [rsp+0A8h+var_28], rax
0x180033bb1  mov     rsi, [rsp+0A8h+arg_20]
0x180033bb9  mov     rbx, r8
0x180033bbc  mov     rcx, rdx; rguid
0x180033bbf  mov     qword ptr [r9], 0
0x180033bc6  mov     r8d, 28h ; '('; cchMax
0x180033bcc  mov     [rsp+0A8h+pv], 0
0x180033bd5  lea     rdx, [rsp+0A8h+sz]; lpsz
0x180033bda  mov     dword ptr [rsp+0A8h+Size], 0
0x180033be2  mov     qword ptr [rsi], 0
0x180033be9  call    cs:__imp_StringFromGUID2
0x180033bef  test    eax, eax
0x180033bf1  js      loc_180033C97
0x180033bf7  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x180033bfc  mov     rcx, rbx; unsigned __int16 *
0x180033bff  lea     r8, [rsp+0A8h+pv]; unsigned __int16 **
0x180033c04  lea     rdx, [rsp+0A8h+sz]; unsigned __int16 *
0x180033c09  call    ?RetrievePrivateData@@YAJPEBG0PEAPEAGPEAK@Z; RetrievePrivateData(ushort const *,ushort const *,ushort * *,ulong *)
0x180033c0e  cmp     eax, 80070002h
0x180033c13  jnz     short loc_180033C1C
0x180033c15  mov     eax, 1
0x180033c1a  jmp     short loc_180033C97
0x180033c1c  test    eax, eax
0x180033c1e  js      short loc_180033C97
0x180033c20  mov     rbx, [rsp+0A8h+pv]
0x180033c25  mov     rcx, rbx; unsigned __int16 *
0x180033c28  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180033c2d  lea     eax, ds:2[rax*2]
0x180033c34  mov     ecx, eax; cb
0x180033c36  mov     edi, eax
0x180033c38  call    cs:__imp_CoTaskMemAlloc
0x180033c3e  mov     [rsi], rax
0x180033c41  test    rax, rax
0x180033c44  jnz     short loc_180033C6D
0x180033c46  xor     ecx, ecx; pv
0x180033c48  call    cs:__imp_CoTaskMemFree
0x180033c4e  mov     eax, dword ptr [rsp+0A8h+Size]
0x180033c52  mov     rcx, rbx
0x180033c55  test    rax, rax
0x180033c58  jz      short loc_180033C66
0x180033c5a  mov     byte ptr [rcx], 0
0x180033c5d  inc     rcx
0x180033c60  sub     rax, 1
0x180033c64  jnz     short loc_180033C5A
0x180033c66  mov     edi, 8007000Eh
0x180033c6b  jmp     short loc_180033C8C
0x180033c6d  mov     r8, rbx; unsigned __int16 *
0x180033c70  mov     rdx, rdi; unsigned __int64
0x180033c73  mov     rcx, rax; unsigned __int16 *
0x180033c76  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c7b  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x180033c80  xor     edx, edx; Val
0x180033c82  mov     rcx, rbx; void *
0x180033c85  mov     edi, eax
0x180033c87  call    memset_0
0x180033c8c  mov     rcx, rbx; pv
0x180033c8f  call    cs:__imp_CoTaskMemFree
0x180033c95  mov     eax, edi
0x180033c97  mov     rcx, [rsp+0A8h+var_28]
0x180033c9f  xor     rcx, rsp; StackCookie
0x180033ca2  call    __security_check_cookie
0x180033ca7  add     rsp, 90h
0x180033cae  pop     rdi
0x180033caf  pop     rsi
0x180033cb0  pop     rbx
0x180033cb1  retn
```
