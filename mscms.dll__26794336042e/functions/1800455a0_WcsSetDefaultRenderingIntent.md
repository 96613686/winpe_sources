# WcsSetDefaultRenderingIntent

- ea: `0x1800455a0`
- end: `0x180045682`
- name: `WcsSetDefaultRenderingIntent`
- size: `226`
- prototype: `BOOL __stdcall(WCS_PROFILE_MANAGEMENT_SCOPE scope, DWORD dwRenderingIntent)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18002e5f0`
- `0x1800431a4`
- `0x1800455a0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180045664`
- `ntdll!EtwEventWrite` at `0x180045664`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800455ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800455ed`

## pseudocode

```c
BOOL __stdcall WcsSetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE scope, DWORD dwRenderingIntent)
{
  DWORD v2; // ecx
  DWORD v4; // eax
  unsigned int v5; // r8d
  __int64 v6; // rcx
  bool v7; // zf
  __int64 *v8; // rdx
  DWORD v9; // [rsp+20h] [rbp-48h] BYREF
  WCS_PROFILE_MANAGEMENT_SCOPE v10; // [rsp+28h] [rbp-40h] BYREF
  DWORD *v11; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v12[3]; // [rsp+38h] [rbp-30h]

  v10 = scope;
  v9 = dwRenderingIntent;
  if ( dwRenderingIntent >= 4 && dwRenderingIntent != -1
    || (unsigned int)scope > WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER
    || dwRenderingIntent == -1 && scope == WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE )
  {
    v2 = 87;
LABEL_7:
    SetLastError(v2);
    return 0;
  }
  v4 = SetDefaultRenderingIntent(scope, dwRenderingIntent);
  if ( v4 )
  {
    v2 = v4;
    goto LABEL_7;
  }
  v5 = 0;
  if ( v9 != -1 )
  {
    v12[0] = 4;
    v11 = &v9;
    v5 = 1;
  }
  v6 = 2LL * v5;
  v7 = v9 == -1;
  v12[v6 - 1] = &v10;
  v8 = SET_DEFAULT_RENDERING_INTENT;
  v12[v6] = 4;
  if ( v7 )
    v8 = (__int64 *)"\t";
  EtwEventWrite(g_etwHandle, v8, v5 + 1, &v11);
  return 1;
}

```

## disassembly

```asm
0x1800455a0  push    rbx
0x1800455a2  sub     rsp, 60h
0x1800455a6  mov     rax, cs:__security_cookie
0x1800455ad  xor     rax, rsp
0x1800455b0  mov     [rsp+68h+var_18], rax
0x1800455b5  or      ebx, 0FFFFFFFFh
0x1800455b8  mov     [rsp+68h+var_40], ecx
0x1800455bc  mov     [rsp+68h+var_48], edx
0x1800455c0  test    edx, edx
0x1800455c2  jz      short loc_1800455D7
0x1800455c4  cmp     edx, 1
0x1800455c7  jz      short loc_1800455D7
0x1800455c9  cmp     edx, 2
0x1800455cc  jz      short loc_1800455D7
0x1800455ce  cmp     edx, 3
0x1800455d1  jz      short loc_1800455D7
0x1800455d3  cmp     edx, ebx
0x1800455d5  jnz     short loc_1800455E8
0x1800455d7  test    ecx, ecx
0x1800455d9  jz      short loc_1800455E0
0x1800455db  cmp     ecx, 1
0x1800455de  jnz     short loc_1800455E8
0x1800455e0  cmp     edx, ebx
0x1800455e2  jnz     short loc_1800455F7
0x1800455e4  test    ecx, ecx
0x1800455e6  jnz     short loc_1800455F7
0x1800455e8  mov     ecx, 57h ; 'W'; dwErrCode
0x1800455ed  call    cs:__imp_SetLastError
0x1800455f3  xor     eax, eax
0x1800455f5  jmp     short loc_18004566F
0x1800455f7  call    ?SetDefaultRenderingIntent@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@K@Z; SetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE,ulong)
0x1800455fc  test    eax, eax
0x1800455fe  jz      short loc_180045604
0x180045600  mov     ecx, eax
0x180045602  jmp     short loc_1800455ED
0x180045604  xor     r8d, r8d
0x180045607  cmp     [rsp+68h+var_48], ebx
0x18004560b  jz      short loc_180045626
0x18004560d  lea     rax, [rsp+68h+var_48]
0x180045612  mov     [rsp+68h+var_30], 4
0x18004561b  mov     [rsp+68h+var_38], rax
0x180045620  mov     r8d, 1
0x180045626  mov     ecx, r8d
0x180045629  lea     rdx, [rsp+68h+var_40]
0x18004562e  add     rcx, rcx
0x180045631  lea     r9, [rsp+68h+var_38]
0x180045636  cmp     [rsp+68h+var_48], ebx
0x18004563a  mov     [rsp+rcx*8+68h+var_38], rdx
0x18004563f  lea     rdx, SET_DEFAULT_RENDERING_INTENT
0x180045646  mov     [rsp+rcx*8+68h+var_30], 4
0x18004564f  lea     rcx, UNSET_DEFAULT_RENDERING_INTENT; "\t"
0x180045656  cmovz   rdx, rcx
0x18004565a  mov     rcx, cs:g_etwHandle
0x180045661  inc     r8d
0x180045664  call    cs:__imp_EtwEventWrite
0x18004566a  mov     eax, 1
0x18004566f  mov     rcx, [rsp+68h+var_18]
0x180045674  xor     rcx, rsp; StackCookie
0x180045677  call    __security_check_cookie
0x18004567c  add     rsp, 60h
0x180045680  pop     rbx
0x180045681  retn
```
