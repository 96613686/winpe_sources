# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z

- ea: `0x1000fdee`
- end: `0x1000fe33`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z`
- size: `69`
- prototype: `_DWORD *__thiscall(HANDLE *this, _DWORD *, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1000fa6a`
- `0x1000fbc9`

## callees

- `0x10007605`
- `0x1000fdee`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x1000fdfb`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000fdfb`

## string_xrefs

- `0x1000fe29`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_DWORD *__thiscall _acquire___mutex_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QBE_AV__unique_any_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_ReleaseMutex_details_wil__YGX0_ZU__integral_constant_I_01_wistd__PAXPAX_0A___T_details_wil___details_wil___2_PAKKH_Z(
        HANDLE *this,
        _DWORD *a2,
        int a3,
        int a4,
        int a5)
{
  HANDLE v5; // esi
  DWORD v6; // eax
  _DWORD *result; // eax

  v5 = *this;
  v6 = WaitForSingleObjectEx(*this, 0xFFFFFFFF, 0);
  if ( v6 == 258 )
  {
    v5 = 0;
  }
  else if ( v6 && v6 != 128 )
  {
    wil::details::in1diag3::FailFast_Unexpected((wil::details::in1diag3 *)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
  }
  result = a2;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x1000fdee  mov     edi, edi
0x1000fdf0  push    ebp; unsigned int
0x1000fdf1  mov     ebp, esp
0x1000fdf3  push    esi; void *
0x1000fdf4  mov     esi, [ecx]
0x1000fdf6  push    0; bAlertable
0x1000fdf8  push    0FFFFFFFFh; dwMilliseconds
0x1000fdfa  push    esi; hHandle
0x1000fdfb  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1000fe01  cmp     eax, 102h
0x1000fe06  jz      short loc_1000FE15
0x1000fe08  test    eax, eax
0x1000fe0a  jz      short loc_1000FE17
0x1000fe0c  cmp     eax, 80h
0x1000fe11  jnz     short loc_1000FE21
0x1000fe13  jmp     short loc_1000FE17
0x1000fe15  xor     esi, esi
0x1000fe17  mov     eax, [ebp+arg_0]
0x1000fe1a  mov     [eax], esi
0x1000fe1c  pop     esi
0x1000fe1d  pop     ebp
0x1000fe1e  retn    10h
0x1000fe21  mov     ecx, [ebp+4]
0x1000fe24  mov     edx, 0E01h
0x1000fe29  push    offset aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1000fe2e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
