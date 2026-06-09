# Resources::FormatSystemMessage(long)

- ea: `0x1003f701`
- end: `0x1003f8b5`
- name: `?FormatSystemMessage@Resources@@SGPAVString@@J@Z`
- size: `436`
- prototype: `String *__userpurge@<eax>(int errorid@<ecx>)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10059412`
- `0x100677b1`
- `0x10077bd0`
- `0x100d6812`
- `0x10142a60`

## callees

- `0x1003f548`
- `0x1003f701`
- `0x1003fba3`
- `0x10040be6`
- `0x10040c44`
- `0x10040dee`
- `0x100559fb`
- `0x10059412`
- `0x1006702a`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x1007a9da`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1003f73a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1003f73a`

## string_xrefs

- `0x1003f7ea`: `URLMON.DLL`
- `0x1003f865`: `URLMON.DLL`
- `0x1003f804`: `WININET.DLL`
- `0x1003f83b`: `WINHTTP.DLL`

## pseudocode

```c
String *__fastcall Resources::FormatSystemMessage(DWORD errorid)
{
  wchar_t *v2; // edi
  DWORD v3; // ecx
  String *v4; // eax
  String *v5; // esi
  String *p; // esi
  String *v8; // esi
  _reference<IInternetSecurityManager> *v9; // eax
  unsigned int v10; // [esp+0h] [ebp-34h]
  unsigned int v11; // [esp+0h] [ebp-34h]
  unsigned int v12; // [esp+0h] [ebp-34h]
  bool v13; // [esp+4h] [ebp-30h]
  bool v14; // [esp+4h] [ebp-30h]
  bool v15; // [esp+4h] [ebp-30h]
  _reference<String> num; // [esp+14h] [ebp-20h] BYREF
  _reference<String> result; // [esp+18h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+1Ch] [ebp-18h]

  v2 = (wchar_t *)_MemAlloc(0x2000u, 0);
  if ( v2 )
  {
    v3 = FormatMessageW(0x1000u, 0, errorid, 0x400u, v2, 0x1000u, 0);
    if ( !v3 )
    {
      v3 = Resources::SafeFormatMessage(errorid, L"URLMON.DLL", v2, 0, (unsigned __int16 *)1, v10, v13);
      if ( !v3 )
      {
        v3 = Resources::SafeFormatMessage(errorid, L"WININET.DLL", v2, 0, (unsigned __int16 *)1, v11, v14);
        if ( !v3
          && ((errorid & 0x1FFF0000) != 0x70000
           || (unsigned int)(unsigned __int16)errorid - 12001 > 0xC0
           || (v3 = Resources::SafeFormatMessage(errorid, L"WINHTTP.DLL", v2, 0, (unsigned __int16 *)1, v12, v15)) == 0)
          && errorid + 2146697216 <= 0x3FF )
        {
          v3 = Resources::SafeFormatMessage(errorid, L"URLMON.DLL", v2, v3, 0, v12, v15);
        }
      }
    }
    num._p = 0;
    result._p = 0;
    ms_exc.registration.TryLevel = 0;
    if ( v3 )
    {
      v2[v3] = 0;
      v4 = String::newString(v2);
    }
    else
    {
      v8 = String::newString(errorid);
      release(&num._p);
      num._p = v8;
      v4 = Resources::formatMessage(0, -1072897270, v8, 0, 0, 0);
    }
    v5 = v4;
    release(&result._p);
    result._p = v5;
    ms_exc.registration.TryLevel = -2;
    MemFree(v2);
    p = result._p;
    result._p = 0;
    release(&result._p);
  }
  else
  {
    v9 = _reference<Node>::_reference<Node>(
           (_reference<IInternetSecurityManager> *)&num,
           (IInternetSecurityManager *)&String::s_cstrEmpty);
    p = (String *)v9->_p;
    v9->_p = 0;
  }
  release(&num._p);
  return p;
}

```

## disassembly

```asm
0x1003f701  push    14h
0x1003f703  push    offset stru_101736F8
0x1003f708  call    __SEH_prolog4
0x1003f70d  mov     esi, errorid
0x1003f70f  xor     edx, edx; dwFlags
0x1003f711  mov     errorid, 2000h; cb
0x1003f716  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1003f71b  mov     edi, eax
0x1003f71d  mov     [ebp+buffer], edi
0x1003f720  test    edi, edi
0x1003f722  jz      loc_1003F7CD
0x1003f728  xor     ebx, ebx
0x1003f72a  push    ebx; Arguments
0x1003f72b  mov     eax, 1000h
0x1003f730  push    eax; nSize
0x1003f731  push    edi; lpBuffer
0x1003f732  push    400h; dwLanguageId
0x1003f737  push    esi; dwMessageId
0x1003f738  push    ebx; lpSource
0x1003f739  push    eax; dwFlags
0x1003f73a  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x1003f740  mov     errorid, eax
0x1003f742  test    errorid, errorid
0x1003f744  jz      loc_1003F7E4
0x1003f74a  mov     [ebp+num._p], ebx
0x1003f74d  mov     [ebp+result._p], ebx
0x1003f750  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1003f753  test    errorid, errorid
0x1003f755  jz      short loc_1003F7A7
0x1003f757  xor     eax, eax
0x1003f759  mov     [edi+errorid*2], ax
0x1003f75d  mov     errorid, edi; c
0x1003f75f  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1003f764  mov     esi, eax
0x1003f766  lea     errorid, [ebp+result]; ppref
0x1003f769  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f76e  mov     [ebp+result._p], esi
0x1003f771  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003f778  mov     errorid, edi; pv
0x1003f77a  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x1003f77f  mov     esi, [ebp+result._p]
0x1003f782  mov     [ebp+result._p], ebx
0x1003f785  lea     errorid, [ebp+result]; ppref
0x1003f788  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f78d  lea     errorid, [ebp+num]; ppref
0x1003f790  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f795  mov     eax, esi
0x1003f797  mov     errorid, [ebp+ms_exc.registration.Next]
0x1003f79a  mov     large fs:0, errorid
0x1003f7a1  pop     errorid
0x1003f7a2  pop     edi
0x1003f7a3  pop     esi
0x1003f7a4  pop     ebx
0x1003f7a5  leave
0x1003f7a6  retn
0x1003f7a7  mov     errorid, esi; c
0x1003f7a9  call    ?newString@String@@SGPAV1@H@Z; String::newString(int)
0x1003f7ae  mov     esi, eax
0x1003f7b0  lea     errorid, [ebp+num]; ppref
0x1003f7b3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f7b8  mov     [ebp+num._p], esi
0x1003f7bb  push    ebx; a4
0x1003f7bc  push    ebx; a3
0x1003f7bd  push    ebx; a2
0x1003f7be  push    esi; a1
0x1003f7bf  mov     edx, 0C00CE30Ah; resid
0x1003f7c4  xor     errorid, errorid; ppParams
0x1003f7c6  call    ?formatMessage@Resources@@SGPAVString@@PAPAV?$_array@V?$_reference@VString@@@@@@JPAV2@111@Z; Resources::formatMessage(_array<_reference<String>> * *,long,String *,String *,String *,String *)
0x1003f7cb  jmp     short loc_1003F764
0x1003f7cd  push    offset ?s_cstrEmpty@String@@2V_CodebaseString@@B; p
0x1003f7d2  lea     errorid, [ebp+num]; this
0x1003f7d5  call    ??0?$_reference@VNode@@@@QAE@PAVNode@@@Z; _reference<Node>::_reference<Node>(Node *)
0x1003f7da  mov     esi, [eax]
0x1003f7dc  mov     dword ptr [eax], 0
0x1003f7e2  jmp     short loc_1003F78D
0x1003f7e4  push    1
0x1003f7e6  push    errorid; fCheckBeforeLoad
0x1003f7e7  push    edi; buffer
0x1003f7e8  mov     edx, esi; errorid
0x1003f7ea  mov     errorid, offset aUrlmonDll; "URLMON.DLL"
0x1003f7ef  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f7f4  mov     errorid, eax
0x1003f7f6  test    errorid, errorid
0x1003f7f8  jnz     done
0x1003f7fe  push    1
0x1003f800  push    errorid; fCheckBeforeLoad
0x1003f801  push    edi; buffer
0x1003f802  mov     edx, esi; errorid
0x1003f804  mov     errorid, offset aWininetDll; "WININET.DLL"
0x1003f809  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f80e  mov     errorid, eax
0x1003f810  test    errorid, errorid
0x1003f812  jnz     done
0x1003f818  mov     eax, esi
0x1003f81a  and     eax, 1FFF0000h
0x1003f81f  cmp     eax, 70000h
0x1003f824  jnz     short loc_1003F84F
0x1003f826  movzx   eax, si
0x1003f829  add     eax, 0FFFFD11Fh
0x1003f82e  cmp     eax, 0C0h
0x1003f833  ja      short loc_1003F84F
0x1003f835  push    1
0x1003f837  push    errorid; fCheckBeforeLoad
0x1003f838  push    edi; buffer
0x1003f839  mov     edx, esi; errorid
0x1003f83b  mov     errorid, offset aWinhttpDll; "WINHTTP.DLL"
0x1003f840  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f845  mov     errorid, eax
0x1003f847  test    errorid, errorid
0x1003f849  jnz     done
0x1003f84f  lea     eax, [esi+7FF40000h]
0x1003f855  cmp     eax, 3FFh
0x1003f85a  ja      done
0x1003f860  push    ebx
0x1003f861  push    errorid; fCheckBeforeLoad
0x1003f862  push    edi; buffer
0x1003f863  mov     edx, esi; errorid
0x1003f865  mov     errorid, offset aUrlmonDll; "URLMON.DLL"
0x1003f86a  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f86f  mov     errorid, eax
0x1003f871  jmp     done
0x1003f876  mov     errorid, [ebp+ms_exc.exc_ptr]; ep
0x1003f879  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1003f87e  retn
0x1003f87f  mov     esp, [ebp+ms_exc.old_esp]
0x1003f882  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1003f887  cmp     [ebp+num._p], 0
0x1003f88b  jz      short loc_1003F897
0x1003f88d  xor     edx, edx; pref
0x1003f88f  lea     errorid, [ebp+num]; ppref
0x1003f892  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1003f897  mov     edx, offset ?s_cstrEmpty@String@@2V_CodebaseString@@B; pref
0x1003f89c  lea     errorid, [ebp+result]; ppref
0x1003f89f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1003f8a4  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003f8ab  xor     ebx, ebx
0x1003f8ad  mov     edi, [ebp+buffer]
0x1003f8b0  jmp     loc_1003F778
```
