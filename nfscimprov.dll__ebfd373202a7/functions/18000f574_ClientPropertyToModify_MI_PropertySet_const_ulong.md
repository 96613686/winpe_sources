# ClientPropertyToModify(_MI_PropertySet const *,ulong *)

- ea: `0x18000f574`
- end: `0x18000f82f`
- name: `?ClientPropertyToModify@@YA?AW4_MI_Result@@PEBU_MI_PropertySet@@PEAK@Z`
- size: `699`
- prototype: `enum _MI_Result __fastcall(const struct _MI_PropertySet *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011ad4`

## callees

- `0x180009704`
- `0x180009744`
- `0x1800097d0`
- `0x18000994c`
- `0x18000eae4`
- `0x18000f574`
- `0x180035b40`
- `0x180037010`

## string_xrefs

- `0x18000f612`: `DefaultAccessMode`
- `0x18000f644`: `MountType`
- `0x18000f676`: `MountRetryAttempts`
- `0x18000f6a8`: `ReadBufferSize`
- `0x18000f70c`: `TransportProtocol`
- `0x18000f770`: `WriteBufferSize`

## pseudocode

```c
__int64 __fastcall ClientPropertyToModify(const struct _MI_PropertySet *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 *v15; // rbx
  _QWORD *v16; // rdx
  unsigned int v17; // eax
  _BYTE v19[16]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD v20[8]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp+17h] BYREF

  stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>(v20);
  v4 = 0;
  std::wstring::wstring(v21, L"Authentication");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 2;
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v21, v5, 0);
  std::wstring::wstring(v21, L"CaseSensitiveLookup");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 4;
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v21, v6, 0);
  std::wstring::wstring(v21, L"DefaultAccessMode");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 8;
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v21, v7, 0);
  std::wstring::wstring(v21, L"MountType");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 16;
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v21, v8, 0);
  std::wstring::wstring(v21, L"MountRetryAttempts");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 32;
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v21, v9, 0);
  std::wstring::wstring(v21, L"ReadBufferSize");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 64;
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v21, v10, 0);
  std::wstring::wstring(v21, L"RpcTimeout");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 128;
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v21, v11, 0);
  std::wstring::wstring(v21, L"TransportProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 256;
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v21, v12, 0);
  std::wstring::wstring(v21, L"UseReservedPorts");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 512;
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v21, v13, 0);
  std::wstring::wstring(v21, L"WriteBufferSize");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v20,
               v21) = 1024;
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(v21, v14, 0);
  v15 = (__int64 *)v20[0];
LABEL_2:
  v15 = (__int64 *)*v15;
  while ( v15 != (__int64 *)v20[0] )
  {
    v19[0] = 0;
    v16 = v15 + 2;
    if ( (unsigned __int64)v15[5] >= 8 )
      v16 = (_QWORD *)*v16;
    if ( !a1 || !a1->ft )
    {
      v4 = 4;
      break;
    }
    v17 = ((__int64 (__fastcall *)(const struct _MI_PropertySet *, _QWORD *, _BYTE *))a1->ft->ContainsElement)(
            a1,
            v16,
            v19);
    v4 = v17;
    if ( !v17 && v19[0] == 1 )
    {
      *a2 |= *((_DWORD *)v15 + 12);
      goto LABEL_2;
    }
    v15 = (__int64 *)*v15;
    if ( v17 )
      break;
  }
  std::_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v20);
  return v4;
}

```

## disassembly

```asm
0x18000f574  mov     [rsp-8+arg_10], rbx
0x18000f579  mov     [rsp-8+arg_18], rsi
0x18000f57e  push    rbp
0x18000f57f  push    rdi
0x18000f580  push    r14
0x18000f582  lea     rbp, [rsp-47h]
0x18000f587  sub     rsp, 0A0h
0x18000f58e  mov     rax, cs:__security_cookie
0x18000f595  xor     rax, rsp
0x18000f598  mov     [rbp+57h+var_20], rax
0x18000f59c  mov     r14, rdx
0x18000f59f  mov     rsi, rcx
0x18000f5a2  lea     rcx, [rbp+57h+var_80]
0x18000f5a6  call    ??0?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAA@XZ; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>(void)
0x18000f5ab  nop
0x18000f5ac  xor     edi, edi
0x18000f5ae  lea     rdx, aAuthentication; "Authentication"
0x18000f5b5  lea     rcx, [rbp+57h+var_40]
0x18000f5b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f5be  nop
0x18000f5bf  lea     rdx, [rbp+57h+var_40]
0x18000f5c3  lea     rcx, [rbp+57h+var_80]
0x18000f5c7  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f5cc  mov     dword ptr [rax], 2
0x18000f5d2  xor     r8d, r8d
0x18000f5d5  mov     dl, 1
0x18000f5d7  lea     rcx, [rbp+57h+var_40]
0x18000f5db  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f5e0  lea     rdx, aCasesensitivel; "CaseSensitiveLookup"
0x18000f5e7  lea     rcx, [rbp+57h+var_40]
0x18000f5eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f5f0  nop
0x18000f5f1  lea     rdx, [rbp+57h+var_40]
0x18000f5f5  lea     rcx, [rbp+57h+var_80]
0x18000f5f9  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f5fe  mov     dword ptr [rax], 4
0x18000f604  xor     r8d, r8d
0x18000f607  mov     dl, 1
0x18000f609  lea     rcx, [rbp+57h+var_40]
0x18000f60d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f612  lea     rdx, aDefaultaccessm; "DefaultAccessMode"
0x18000f619  lea     rcx, [rbp+57h+var_40]
0x18000f61d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f622  nop
0x18000f623  lea     rdx, [rbp+57h+var_40]
0x18000f627  lea     rcx, [rbp+57h+var_80]
0x18000f62b  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f630  mov     dword ptr [rax], 8
0x18000f636  xor     r8d, r8d
0x18000f639  mov     dl, 1
0x18000f63b  lea     rcx, [rbp+57h+var_40]
0x18000f63f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f644  lea     rdx, aMounttype; "MountType"
0x18000f64b  lea     rcx, [rbp+57h+var_40]
0x18000f64f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f654  nop
0x18000f655  lea     rdx, [rbp+57h+var_40]
0x18000f659  lea     rcx, [rbp+57h+var_80]
0x18000f65d  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f662  mov     dword ptr [rax], 10h
0x18000f668  xor     r8d, r8d
0x18000f66b  mov     dl, 1
0x18000f66d  lea     rcx, [rbp+57h+var_40]
0x18000f671  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f676  lea     rdx, aMountretryatte; "MountRetryAttempts"
0x18000f67d  lea     rcx, [rbp+57h+var_40]
0x18000f681  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f686  nop
0x18000f687  lea     rdx, [rbp+57h+var_40]
0x18000f68b  lea     rcx, [rbp+57h+var_80]
0x18000f68f  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f694  mov     dword ptr [rax], 20h ; ' '
0x18000f69a  xor     r8d, r8d
0x18000f69d  mov     dl, 1
0x18000f69f  lea     rcx, [rbp+57h+var_40]
0x18000f6a3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f6a8  lea     rdx, aReadbuffersize; "ReadBufferSize"
0x18000f6af  lea     rcx, [rbp+57h+var_40]
0x18000f6b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f6b8  nop
0x18000f6b9  lea     rdx, [rbp+57h+var_40]
0x18000f6bd  lea     rcx, [rbp+57h+var_80]
0x18000f6c1  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f6c6  mov     dword ptr [rax], 40h ; '@'
0x18000f6cc  xor     r8d, r8d
0x18000f6cf  mov     dl, 1
0x18000f6d1  lea     rcx, [rbp+57h+var_40]
0x18000f6d5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f6da  lea     rdx, aRpctimeout; "RpcTimeout"
0x18000f6e1  lea     rcx, [rbp+57h+var_40]
0x18000f6e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f6ea  nop
0x18000f6eb  lea     rdx, [rbp+57h+var_40]
0x18000f6ef  lea     rcx, [rbp+57h+var_80]
0x18000f6f3  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f6f8  mov     dword ptr [rax], 80h
0x18000f6fe  xor     r8d, r8d
0x18000f701  mov     dl, 1
0x18000f703  lea     rcx, [rbp+57h+var_40]
0x18000f707  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f70c  lea     rdx, aTransportproto; "TransportProtocol"
0x18000f713  lea     rcx, [rbp+57h+var_40]
0x18000f717  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f71c  nop
0x18000f71d  lea     rdx, [rbp+57h+var_40]
0x18000f721  lea     rcx, [rbp+57h+var_80]
0x18000f725  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f72a  mov     dword ptr [rax], 100h
0x18000f730  xor     r8d, r8d
0x18000f733  mov     dl, 1
0x18000f735  lea     rcx, [rbp+57h+var_40]
0x18000f739  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f73e  lea     rdx, aUsereservedpor; "UseReservedPorts"
0x18000f745  lea     rcx, [rbp+57h+var_40]
0x18000f749  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f74e  nop
0x18000f74f  lea     rdx, [rbp+57h+var_40]
0x18000f753  lea     rcx, [rbp+57h+var_80]
0x18000f757  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f75c  mov     dword ptr [rax], 200h
0x18000f762  xor     r8d, r8d
0x18000f765  mov     dl, 1
0x18000f767  lea     rcx, [rbp+57h+var_40]
0x18000f76b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f770  lea     rdx, aWritebuffersiz; "WriteBufferSize"
0x18000f777  lea     rcx, [rbp+57h+var_40]
0x18000f77b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000f780  nop
0x18000f781  lea     rdx, [rbp+57h+var_40]
0x18000f785  lea     rcx, [rbp+57h+var_80]
0x18000f789  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18000f78e  mov     dword ptr [rax], 400h
0x18000f794  xor     r8d, r8d
0x18000f797  mov     dl, 1
0x18000f799  lea     rcx, [rbp+57h+var_40]
0x18000f79d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f7a2  mov     rbx, [rbp+57h+var_80]
0x18000f7a6  mov     rbx, [rbx]
0x18000f7a9  cmp     rbx, [rbp+57h+var_80]
0x18000f7ad  jz      short loc_18000F800
0x18000f7af  mov     [rbp+57h+var_90], 0
0x18000f7b3  lea     rdx, [rbx+10h]
0x18000f7b7  cmp     qword ptr [rbx+28h], 8
0x18000f7bc  jb      short loc_18000F7C1
0x18000f7be  mov     rdx, [rdx]
0x18000f7c1  test    rsi, rsi
0x18000f7c4  jz      short loc_18000F7FB
0x18000f7c6  mov     rax, [rsi]
0x18000f7c9  test    rax, rax
0x18000f7cc  jz      short loc_18000F7FB
0x18000f7ce  lea     r8, [rbp+57h+var_90]
0x18000f7d2  mov     rcx, rsi
0x18000f7d5  mov     rax, [rax+8]
0x18000f7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7de  mov     edi, eax
0x18000f7e0  test    eax, eax
0x18000f7e2  jnz     short loc_18000F7F2
0x18000f7e4  cmp     [rbp+57h+var_90], 1
0x18000f7e8  jnz     short loc_18000F7F2
0x18000f7ea  mov     eax, [rbx+30h]
0x18000f7ed  or      [r14], eax
0x18000f7f0  jmp     short loc_18000F7A6
0x18000f7f2  mov     rbx, [rbx]
0x18000f7f5  test    eax, eax
0x18000f7f7  jz      short loc_18000F7A9
0x18000f7f9  jmp     short loc_18000F800
0x18000f7fb  mov     edi, 4
0x18000f800  lea     rcx, [rbp+57h+var_80]
0x18000f804  call    ??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hmap_traits<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x18000f809  mov     eax, edi
0x18000f80b  mov     rcx, [rbp+57h+var_20]
0x18000f80f  xor     rcx, rsp; StackCookie
0x18000f812  call    __security_check_cookie
0x18000f817  lea     r11, [rsp+0B0h+var_10]
0x18000f81f  mov     rbx, [r11+30h]
0x18000f823  mov     rsi, [r11+38h]
0x18000f827  mov     rsp, r11
0x18000f82a  pop     r14
0x18000f82c  pop     rdi
0x18000f82d  pop     rbp
0x18000f82e  retn
```
