# Resources::FormatSystemMessage(long)

- ea: `0x1003f671`
- end: `0x1003f825`
- name: `?FormatSystemMessage@Resources@@SGPAVString@@J@Z`
- size: `436`
- prototype: `String *__userpurge@<eax>(int errorid@<ecx>)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10059382`
- `0x10067711`
- `0x10077c00`
- `0x100d6932`
- `0x10142b70`

## callees

- `0x1003f4b8`
- `0x1003f671`
- `0x1003fb13`
- `0x10040b56`
- `0x10040bb4`
- `0x10040d5e`
- `0x1005596b`
- `0x10059382`
- `0x10066f8a`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x1007aa1a`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1003f6aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1003f6aa`

## string_xrefs

- `0x1003f75a`: `URLMON.DLL`
- `0x1003f7d5`: `URLMON.DLL`
- `0x1003f774`: `WININET.DLL`
- `0x1003f7ab`: `WINHTTP.DLL`

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
0x1003f671  push    14h
0x1003f673  push    offset stru_101737E8
0x1003f678  call    __SEH_prolog4
0x1003f67d  mov     esi, errorid
0x1003f67f  xor     edx, edx; dwFlags
0x1003f681  mov     errorid, 2000h; cb
0x1003f686  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1003f68b  mov     edi, eax
0x1003f68d  mov     [ebp+buffer], edi
0x1003f690  test    edi, edi
0x1003f692  jz      loc_1003F73D
0x1003f698  xor     ebx, ebx
0x1003f69a  push    ebx; Arguments
0x1003f69b  mov     eax, 1000h
0x1003f6a0  push    eax; nSize
0x1003f6a1  push    edi; lpBuffer
0x1003f6a2  push    400h; dwLanguageId
0x1003f6a7  push    esi; dwMessageId
0x1003f6a8  push    ebx; lpSource
0x1003f6a9  push    eax; dwFlags
0x1003f6aa  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x1003f6b0  mov     errorid, eax
0x1003f6b2  test    errorid, errorid
0x1003f6b4  jz      loc_1003F754
0x1003f6ba  mov     [ebp+num._p], ebx
0x1003f6bd  mov     [ebp+result._p], ebx
0x1003f6c0  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1003f6c3  test    errorid, errorid
0x1003f6c5  jz      short loc_1003F717
0x1003f6c7  xor     eax, eax
0x1003f6c9  mov     [edi+errorid*2], ax
0x1003f6cd  mov     errorid, edi; c
0x1003f6cf  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1003f6d4  mov     esi, eax
0x1003f6d6  lea     errorid, [ebp+result]; ppref
0x1003f6d9  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f6de  mov     [ebp+result._p], esi
0x1003f6e1  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003f6e8  mov     errorid, edi; pv
0x1003f6ea  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x1003f6ef  mov     esi, [ebp+result._p]
0x1003f6f2  mov     [ebp+result._p], ebx
0x1003f6f5  lea     errorid, [ebp+result]; ppref
0x1003f6f8  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f6fd  lea     errorid, [ebp+num]; ppref
0x1003f700  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f705  mov     eax, esi
0x1003f707  mov     errorid, [ebp+ms_exc.registration.Next]
0x1003f70a  mov     large fs:0, errorid
0x1003f711  pop     errorid
0x1003f712  pop     edi
0x1003f713  pop     esi
0x1003f714  pop     ebx
0x1003f715  leave
0x1003f716  retn
0x1003f717  mov     errorid, esi; c
0x1003f719  call    ?newString@String@@SGPAV1@H@Z; String::newString(int)
0x1003f71e  mov     esi, eax
0x1003f720  lea     errorid, [ebp+num]; ppref
0x1003f723  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1003f728  mov     [ebp+num._p], esi
0x1003f72b  push    ebx; a4
0x1003f72c  push    ebx; a3
0x1003f72d  push    ebx; a2
0x1003f72e  push    esi; a1
0x1003f72f  mov     edx, 0C00CE30Ah; resid
0x1003f734  xor     errorid, errorid; ppParams
0x1003f736  call    ?formatMessage@Resources@@SGPAVString@@PAPAV?$_array@V?$_reference@VString@@@@@@JPAV2@111@Z; Resources::formatMessage(_array<_reference<String>> * *,long,String *,String *,String *,String *)
0x1003f73b  jmp     short loc_1003F6D4
0x1003f73d  push    offset ?s_cstrEmpty@String@@2V_CodebaseString@@B; p
0x1003f742  lea     errorid, [ebp+num]; this
0x1003f745  call    ??0?$_reference@VNode@@@@QAE@PAVNode@@@Z; _reference<Node>::_reference<Node>(Node *)
0x1003f74a  mov     esi, [eax]
0x1003f74c  mov     dword ptr [eax], 0
0x1003f752  jmp     short loc_1003F6FD
0x1003f754  push    1
0x1003f756  push    errorid; fCheckBeforeLoad
0x1003f757  push    edi; buffer
0x1003f758  mov     edx, esi; errorid
0x1003f75a  mov     errorid, offset aUrlmonDll; "URLMON.DLL"
0x1003f75f  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f764  mov     errorid, eax
0x1003f766  test    errorid, errorid
0x1003f768  jnz     done
0x1003f76e  push    1
0x1003f770  push    errorid; fCheckBeforeLoad
0x1003f771  push    edi; buffer
0x1003f772  mov     edx, esi; errorid
0x1003f774  mov     errorid, offset aWininetDll; "WININET.DLL"
0x1003f779  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f77e  mov     errorid, eax
0x1003f780  test    errorid, errorid
0x1003f782  jnz     done
0x1003f788  mov     eax, esi
0x1003f78a  and     eax, 1FFF0000h
0x1003f78f  cmp     eax, 70000h
0x1003f794  jnz     short loc_1003F7BF
0x1003f796  movzx   eax, si
0x1003f799  add     eax, 0FFFFD11Fh
0x1003f79e  cmp     eax, 0C0h
0x1003f7a3  ja      short loc_1003F7BF
0x1003f7a5  push    1
0x1003f7a7  push    errorid; fCheckBeforeLoad
0x1003f7a8  push    edi; buffer
0x1003f7a9  mov     edx, esi; errorid
0x1003f7ab  mov     errorid, offset aWinhttpDll; "WINHTTP.DLL"
0x1003f7b0  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f7b5  mov     errorid, eax
0x1003f7b7  test    errorid, errorid
0x1003f7b9  jnz     done
0x1003f7bf  lea     eax, [esi+7FF40000h]
0x1003f7c5  cmp     eax, 3FFh
0x1003f7ca  ja      done
0x1003f7d0  push    ebx
0x1003f7d1  push    errorid; fCheckBeforeLoad
0x1003f7d2  push    edi; buffer
0x1003f7d3  mov     edx, esi; errorid
0x1003f7d5  mov     errorid, offset aUrlmonDll; "URLMON.DLL"
0x1003f7da  call    ?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1003f7df  mov     errorid, eax
0x1003f7e1  jmp     done
0x1003f7e6  mov     errorid, [ebp+ms_exc.exc_ptr]; ep
0x1003f7e9  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1003f7ee  retn
0x1003f7ef  mov     esp, [ebp+ms_exc.old_esp]
0x1003f7f2  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1003f7f7  cmp     [ebp+num._p], 0
0x1003f7fb  jz      short loc_1003F807
0x1003f7fd  xor     edx, edx; pref
0x1003f7ff  lea     errorid, [ebp+num]; ppref
0x1003f802  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1003f807  mov     edx, offset ?s_cstrEmpty@String@@2V_CodebaseString@@B; pref
0x1003f80c  lea     errorid, [ebp+result]; ppref
0x1003f80f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1003f814  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003f81b  xor     ebx, ebx
0x1003f81d  mov     edi, [ebp+buffer]
0x1003f820  jmp     loc_1003F6E8
```
