# CActiveXInstallSecurityManager::GetSecurityId(uchar *,ulong *,unsigned __int64)

- ea: `0x14000be30`
- end: `0x14000be79`
- name: `?GetSecurityId@CActiveXInstallSecurityManager@@UEAAJPEAEPEAK_K@Z`
- size: `73`
- prototype: `__int64 __fastcall(CActiveXInstallSecurityManager *__hidden this, unsigned __int8 *, unsigned int *, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000be30`

## import_xrefs

- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x14000be67`
- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x14000be67`

## pseudocode

```c
__int64 __fastcall CActiveXInstallSecurityManager::GetSecurityId(
        CActiveXInstallSecurityManager *this,
        unsigned __int8 *a2,
        unsigned int *a3,
        __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx

  result = 2147500037LL;
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    v7 = *((_QWORD *)this + 3);
    if ( v7 )
    {
      if ( a3 )
      {
        if ( *a3 >= 0x200 )
          return GetZoneAgnosticSecurityIdFromUrl(v7, v6, a2, a3, a4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000be30  sub     rsp, 38h
0x14000be34  mov     r10, rdx
0x14000be37  mov     eax, 80004005h
0x14000be3c  mov     rdx, [rcx+10h]
0x14000be40  test    rdx, rdx
0x14000be43  jz      short loc_14000BE73
0x14000be45  mov     rcx, [rcx+18h]
0x14000be49  test    rcx, rcx
0x14000be4c  jz      short loc_14000BE73
0x14000be4e  test    r8, r8
0x14000be51  jz      short loc_14000BE73
0x14000be53  cmp     dword ptr [r8], 200h
0x14000be5a  jb      short loc_14000BE73
0x14000be5c  mov     [rsp+38h+var_18], r9
0x14000be61  mov     r9, r8
0x14000be64  mov     r8, r10
0x14000be67  call    cs:__imp_GetZoneAgnosticSecurityIdFromUrl
0x14000be6e  nop     dword ptr [rax+rax+00h]
0x14000be73  add     rsp, 38h
0x14000be77  retn
```
