# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x10007aee`
- end: `0x10007bc7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CGJPBG_NPA_KPA_N@Z`
- size: `217`
- prototype: `int __userpurge@<eax>(wchar_t *@<ecx>, unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1000fa6a`

## callees

- `0x100068a9`
- `0x1000697b`
- `0x100075ad`
- `0x100075cd`
- `0x10007630`
- `0x100079cb`
- `0x10007aee`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10007b4d`
- `KERNEL32!GetLastError` at `0x10007b4d`
- `KERNEL32!OpenSemaphoreW` at `0x10007b41`
- `KERNEL32!OpenSemaphoreW` at `0x10007b41`

## pseudocode

```c
int __userpurge wil::details_abi::SemaphoreValue::TryGetValueInternal@<eax>(
        wchar_t *a1@<ecx>,
        unsigned __int16 *a2,
        bool a3,
        unsigned __int64 *a4,
        bool *a5)
{
  int LastError; // edi
  HANDLE v6; // eax
  void *v7; // esi
  void *ValueFromSemaphore; // eax
  const wchar_t *v10; // [esp+0h] [ebp-220h]
  unsigned int v11; // [esp+0h] [ebp-220h]
  void *v12; // [esp+0h] [ebp-220h]
  size_t v13; // [esp+4h] [ebp-21Ch]
  const unsigned __int16 *v14; // [esp+4h] [ebp-21Ch]
  const char *v15; // [esp+4h] [ebp-21Ch]
  const char *v16; // [esp+8h] [ebp-218h]
  int v17; // [esp+Ch] [ebp-214h] BYREF
  WCHAR Name[262]; // [esp+10h] [ebp-210h] BYREF
  int retaddr; // [esp+224h] [ebp+4h]

  LastError = 0;
  *(_DWORD *)a2 = 0;
  *((_DWORD *)a2 + 1) = 0;
  StringCopyWorkerW(a1, (size_t)a1, (size_t *)a1, v10, v13);
  StringCchCatW(Name, L"_p0", v11, v14);
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v7 = v6;
  if ( v6 )
  {
    v17 = 0;
    ValueFromSemaphore = (void *)wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v17);
    LastError = (int)ValueFromSemaphore;
    if ( (int)ValueFromSemaphore >= 0 )
    {
      LastError = 0;
      *(_QWORD *)a2 = v17;
LABEL_9:
      wil::details::CloseHandle(v7, v12);
      return LastError;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (wil::details::in1diag3 *)"wil",
      ValueFromSemaphore,
      (unsigned int)v12,
      v15,
      (int)v16);
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (wil::details::in1diag3 *)"wil",
                  v12,
                  (unsigned int)v15,
                  v16);
  }
  if ( v7 )
    goto LABEL_9;
  return LastError;
}

```

## disassembly

```asm
0x10007aee  mov     edi, edi
0x10007af0  push    ebp
0x10007af1  mov     ebp, esp
0x10007af3  and     esp, 0FFFFFFF8h
0x10007af6  sub     esp, 214h
0x10007afc  mov     eax, ___security_cookie
0x10007b01  xor     eax, esp
0x10007b03  mov     [esp+214h+var_4], eax
0x10007b0a  push    ebx; int
0x10007b0b  mov     ebx, [ebp+arg_0]
0x10007b0e  mov     edx, 104h
0x10007b13  push    esi; char *
0x10007b14  push    edi; void *
0x10007b15  push    ecx; pcchNewDestLength
0x10007b16  push    ecx; cchDest
0x10007b17  xor     edi, edi
0x10007b19  push    ecx; pszDest
0x10007b1a  lea     ecx, [esp+22Ch+Name]
0x10007b1e  mov     [ebx], edi
0x10007b20  mov     [ebx+4], edi
0x10007b23  call    StringCopyWorkerW
0x10007b28  push    offset aP0; "_p0"
0x10007b2d  lea     ecx, [esp+224h+Name]
0x10007b31  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x10007b36  lea     eax, [esp+220h+Name]
0x10007b3a  push    eax; lpName
0x10007b3b  push    edi; bInheritHandle
0x10007b3c  push    1F0003h; dwDesiredAccess
0x10007b41  call    ds:__imp__OpenSemaphoreW@12; OpenSemaphoreW(x,x,x)
0x10007b47  mov     esi, eax
0x10007b49  test    esi, esi
0x10007b4b  jnz     short loc_10007B6E
0x10007b4d  call    ds:__imp__GetLastError@0; GetLastError()
0x10007b53  cmp     eax, 2
0x10007b56  jz      short loc_10007B96
0x10007b58  mov     ecx, [ebp+4]
0x10007b5b  mov     edx, 0D0h
0x10007b60  push    offset aWil; "wil"
0x10007b65  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x10007b6a  mov     edi, eax
0x10007b6c  jmp     short loc_10007B96
0x10007b6e  lea     edx, [esp+220h+var_214]
0x10007b72  mov     [esp+220h+var_214], edi
0x10007b76  mov     ecx, esi
0x10007b78  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CGJPAXPAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x10007b7d  mov     edi, eax
0x10007b7f  test    edi, edi
0x10007b81  jns     short loc_10007B9C
0x10007b83  mov     ecx, [ebp+4]
0x10007b86  mov     edx, 0D6h
0x10007b8b  push    edi; void *
0x10007b8c  push    offset aWil; "wil"
0x10007b91  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10007b96  test    esi, esi
0x10007b98  jz      short loc_10007BAE
0x10007b9a  jmp     short loc_10007BA8
0x10007b9c  mov     eax, [esp+220h+var_214]
0x10007ba0  xor     edi, edi
0x10007ba2  cdq
0x10007ba3  mov     [ebx], eax
0x10007ba5  mov     [ebx+4], edx
0x10007ba8  push    esi; hObject
0x10007ba9  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x10007bae  mov     ecx, [esp+220h+var_4]
0x10007bb5  mov     eax, edi
0x10007bb7  pop     edi
0x10007bb8  pop     esi
0x10007bb9  pop     ebx
0x10007bba  xor     ecx, esp; StackCookie
0x10007bbc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10007bc1  mov     esp, ebp
0x10007bc3  pop     ebp
0x10007bc4  retn    8
```
