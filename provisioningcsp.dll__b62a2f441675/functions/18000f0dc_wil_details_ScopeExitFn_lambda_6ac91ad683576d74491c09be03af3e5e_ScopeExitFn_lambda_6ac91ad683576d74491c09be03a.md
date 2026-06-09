# wil::details::ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___::_ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___

- ea: `0x18000f0dc`
- end: `0x18000f14a`
- name: `wil::details::ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___::_ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f1a0`

## callees

- `0x18000f0dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f132`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f110`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f110`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___::_ScopeExitFn__lambda_6ac91ad683576d74491c09be03af3e5e___(
        __int64 a1)
{
  LPVOID *v2; // rdx
  __int64 v3; // rdi
  LPVOID *v4; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v2 = *(LPVOID **)a1;
    if ( **(_QWORD **)a1 )
    {
      v3 = 0;
      do
      {
        v4 = v2;
        if ( (unsigned int)v3 >= **(_DWORD **)(a1 + 8) )
          break;
        SysFreeString(*((BSTR *)*v2 + v3));
        v2 = *(LPVOID **)a1;
        v3 = (unsigned int)(v3 + 1);
        v4 = *(LPVOID **)a1;
      }
      while ( **(_QWORD **)a1 );
    }
    else
    {
      v4 = *(LPVOID **)a1;
    }
    CoTaskMemFree(*v4);
  }
}

```

## disassembly

```asm
0x18000f0dc  mov     [rsp+arg_0], rbx
0x18000f0e1  push    rdi
0x18000f0e2  sub     rsp, 20h
0x18000f0e6  cmp     byte ptr [rcx+10h], 0
0x18000f0ea  mov     rbx, rcx
0x18000f0ed  jz      short loc_18000F13E
0x18000f0ef  mov     byte ptr [rcx+10h], 0
0x18000f0f3  mov     rdx, [rcx]
0x18000f0f6  cmp     qword ptr [rdx], 0
0x18000f0fa  jz      short loc_18000F12C
0x18000f0fc  xor     edi, edi
0x18000f0fe  mov     rax, [rbx+8]
0x18000f102  mov     rcx, rdx
0x18000f105  cmp     edi, [rax]
0x18000f107  jnb     short loc_18000F12F
0x18000f109  mov     rcx, [rdx]
0x18000f10c  mov     rcx, [rcx+rdi*8]; bstrString
0x18000f110  call    cs:__imp_SysFreeString
0x18000f117  nop     dword ptr [rax+rax+00h]
0x18000f11c  mov     rdx, [rbx]
0x18000f11f  inc     edi
0x18000f121  mov     rcx, rdx
0x18000f124  cmp     qword ptr [rdx], 0
0x18000f128  jnz     short loc_18000F0FE
0x18000f12a  jmp     short loc_18000F12F
0x18000f12c  mov     rcx, rdx
0x18000f12f  mov     rcx, [rcx]; pv
0x18000f132  call    cs:__imp_CoTaskMemFree
0x18000f139  nop     dword ptr [rax+rax+00h]
0x18000f13e  mov     rbx, [rsp+28h+arg_0]
0x18000f143  add     rsp, 20h
0x18000f147  pop     rdi
0x18000f148  retn
```
