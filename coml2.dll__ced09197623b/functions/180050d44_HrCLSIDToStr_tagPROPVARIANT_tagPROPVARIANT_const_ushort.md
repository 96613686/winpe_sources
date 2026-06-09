# HrCLSIDToStr(tagPROPVARIANT *,tagPROPVARIANT const *,ushort)

- ea: `0x180050d44`
- end: `0x180050dec`
- name: `?HrCLSIDToStr@@YAJPEAUtagPROPVARIANT@@PEBU1@G@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180051960`
- `0x180051b64`

## callees

- `0x180050d44`
- `0x180052880`
- `0x180052948`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180050d6e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180050d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dd4`

## pseudocode

```c
__int64 __fastcall HrCLSIDToStr(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2, unsigned __int16 a3)
{
  int v3; // esi
  unsigned int v5; // ebx
  unsigned int v6; // eax
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v3 = a3;
  pv = 0;
  v5 = StringFromCLSID(a2->puuid, (LPOLESTR *)&pv);
  if ( !v5 )
  {
    if ( v3 == 8 )
    {
      v6 = HrWStrToBStr((const unsigned __int16 *)pv, &a1->bstrVal);
    }
    else
    {
      if ( v3 != 30 )
      {
        if ( v3 == 31 )
        {
          a1->hVal.QuadPart = (LONGLONG)pv;
          pv = 0;
        }
LABEL_9:
        a1->vt = v3;
        goto LABEL_10;
      }
      v6 = HrWStrToAStr((LPCWCH)pv, &a1->pszVal);
    }
    v5 = v6;
    if ( v6 )
      goto LABEL_10;
    goto LABEL_9;
  }
LABEL_10:
  if ( pv )
    CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x180050d44  mov     r11, rsp
0x180050d47  mov     [r11+8], rbx
0x180050d4b  mov     [r11+18h], rsi
0x180050d4f  push    rdi
0x180050d50  sub     rsp, 20h
0x180050d54  mov     rax, rdx
0x180050d57  movzx   esi, r8w
0x180050d5b  mov     rdi, rcx
0x180050d5e  mov     qword ptr [r11+10h], 0
0x180050d66  lea     rdx, [r11+10h]; lplpsz
0x180050d6a  mov     rcx, [rax+8]; rclsid
0x180050d6e  call    cs:__imp_StringFromCLSID
0x180050d74  mov     ebx, eax
0x180050d76  test    eax, eax
0x180050d78  jnz     short loc_180050DCA
0x180050d7a  mov     r9d, esi
0x180050d7d  sub     r9d, 8
0x180050d81  jz      short loc_180050DB3
0x180050d83  sub     r9d, 16h
0x180050d87  jz      short loc_180050DA3
0x180050d89  cmp     r9d, 1
0x180050d8d  jnz     short loc_180050DC7
0x180050d8f  mov     rax, [rsp+28h+pv]
0x180050d94  mov     [rdi+8], rax
0x180050d98  mov     [rsp+28h+pv], 0
0x180050da1  jmp     short loc_180050DC7
0x180050da3  mov     rcx, [rsp+28h+pv]; lpWideCharStr
0x180050da8  lea     rdx, [rdi+8]; char **
0x180050dac  call    ?HrWStrToAStr@@YAJPEBGPEAPEAD@Z; HrWStrToAStr(ushort const *,char * *)
0x180050db1  jmp     short loc_180050DC1
0x180050db3  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x180050db8  lea     rdx, [rdi+8]; unsigned __int16 **
0x180050dbc  call    ?HrWStrToBStr@@YAJPEBGPEAPEAG@Z; HrWStrToBStr(ushort const *,ushort * *)
0x180050dc1  mov     ebx, eax
0x180050dc3  test    eax, eax
0x180050dc5  jnz     short loc_180050DCA
0x180050dc7  mov     [rdi], si
0x180050dca  mov     rcx, [rsp+28h+pv]; pv
0x180050dcf  test    rcx, rcx
0x180050dd2  jz      short loc_180050DDA
0x180050dd4  call    cs:__imp_CoTaskMemFree
0x180050dda  mov     rsi, [rsp+28h+arg_10]
0x180050ddf  mov     eax, ebx
0x180050de1  mov     rbx, [rsp+28h+arg_0]
0x180050de6  add     rsp, 20h
0x180050dea  pop     rdi
0x180050deb  retn
```
