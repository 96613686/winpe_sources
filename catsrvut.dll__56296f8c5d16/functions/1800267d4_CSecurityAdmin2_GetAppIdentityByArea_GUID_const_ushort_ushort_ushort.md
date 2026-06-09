# CSecurityAdmin2::GetAppIdentityByArea(_GUID const &,ushort *,ushort * *,ushort * *)

- ea: `0x1800267d4`
- end: `0x1800268f2`
- name: `?GetAppIdentityByArea@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAGPEAPEAG2@Z`
- size: `286`
- prototype: `int(CSecurityAdmin2 *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800267b0`
- `0x180026900`

## callees

- `0x180015594`
- `0x18001c6a4`
- `0x1800267d4`
- `0x180027228`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800268cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800268cf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026829`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026878`

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
0x1800267d4  push    rbx
0x1800267d6  push    rsi
0x1800267d7  push    rdi
0x1800267d8  sub     rsp, 90h
0x1800267df  mov     rax, cs:__security_cookie
0x1800267e6  xor     rax, rsp
0x1800267e9  mov     [rsp+0A8h+var_28], rax
0x1800267f1  mov     rsi, [rsp+0A8h+arg_20]
0x1800267f9  mov     rbx, r8
0x1800267fc  mov     rcx, rdx; rguid
0x1800267ff  mov     qword ptr [r9], 0
0x180026806  mov     r8d, 28h ; '('; cchMax
0x18002680c  mov     [rsp+0A8h+pv], 0
0x180026815  lea     rdx, [rsp+0A8h+sz]; lpsz
0x18002681a  mov     dword ptr [rsp+0A8h+Size], 0
0x180026822  mov     qword ptr [rsi], 0
0x180026829  call    cs:__imp_StringFromGUID2
0x18002682f  test    eax, eax
0x180026831  js      loc_1800268D7
0x180026837  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18002683c  mov     rcx, rbx; unsigned __int16 *
0x18002683f  lea     r8, [rsp+0A8h+pv]; unsigned __int16 **
0x180026844  lea     rdx, [rsp+0A8h+sz]; unsigned __int16 *
0x180026849  call    ?RetrievePrivateData@@YAJPEBG0PEAPEAGPEAK@Z; RetrievePrivateData(ushort const *,ushort const *,ushort * *,ulong *)
0x18002684e  cmp     eax, 80070002h
0x180026853  jnz     short loc_18002685C
0x180026855  mov     eax, 1
0x18002685a  jmp     short loc_1800268D7
0x18002685c  test    eax, eax
0x18002685e  js      short loc_1800268D7
0x180026860  mov     rbx, [rsp+0A8h+pv]
0x180026865  mov     rcx, rbx; unsigned __int16 *
0x180026868  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002686d  lea     eax, ds:2[rax*2]
0x180026874  mov     ecx, eax; cb
0x180026876  mov     edi, eax
0x180026878  call    cs:__imp_CoTaskMemAlloc
0x18002687e  mov     [rsi], rax
0x180026881  test    rax, rax
0x180026884  jnz     short loc_1800268AD
0x180026886  xor     ecx, ecx; pv
0x180026888  call    cs:__imp_CoTaskMemFree
0x18002688e  mov     eax, dword ptr [rsp+0A8h+Size]
0x180026892  mov     rcx, rbx
0x180026895  test    rax, rax
0x180026898  jz      short loc_1800268A6
0x18002689a  mov     byte ptr [rcx], 0
0x18002689d  inc     rcx
0x1800268a0  sub     rax, 1
0x1800268a4  jnz     short loc_18002689A
0x1800268a6  mov     edi, 8007000Eh
0x1800268ab  jmp     short loc_1800268CC
0x1800268ad  mov     r8, rbx; unsigned __int16 *
0x1800268b0  mov     rdx, rdi; unsigned __int64
0x1800268b3  mov     rcx, rax; unsigned __int16 *
0x1800268b6  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800268bb  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x1800268c0  xor     edx, edx; Val
0x1800268c2  mov     rcx, rbx; void *
0x1800268c5  mov     edi, eax
0x1800268c7  call    memset_0
0x1800268cc  mov     rcx, rbx; pv
0x1800268cf  call    cs:__imp_CoTaskMemFree
0x1800268d5  mov     eax, edi
0x1800268d7  mov     rcx, [rsp+0A8h+var_28]
0x1800268df  xor     rcx, rsp; StackCookie
0x1800268e2  call    __security_check_cookie
0x1800268e7  add     rsp, 90h
0x1800268ee  pop     rdi
0x1800268ef  pop     rsi
0x1800268f0  pop     rbx
0x1800268f1  retn
```
