# GetLinkInfoData

- ea: `0x180005570`
- end: `0x1800055ce`
- name: `GetLinkInfoData`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004f44`
- `0x180005570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055a2`

## pseudocode

```c
__int64 __fastcall GetLinkInfoData(__int64 a1, int a2, _QWORD *a3)
{
  int v4; // ecx
  bool v5; // zf
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx

  if ( a2 > 6 )
  {
    v5 = a2 == 7;
    v4 = a2 - 7;
  }
  else
  {
    if ( a2 == 6 )
      goto LABEL_11;
    v4 = a2;
    v5 = a2 == 0;
  }
  if ( !v5 )
  {
    v6 = v4 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( (unsigned int)(v8 - 1) >= 2 )
            goto LABEL_9;
        }
      }
    }
  }
LABEL_11:
  if ( !a3 )
  {
LABEL_9:
    SetLastError(0x57u);
    return 0;
  }
  return GetILinkInfoData(a1, a2, a3);
}

```

## disassembly

```asm
0x180005570  sub     rsp, 28h
0x180005574  mov     r9, rcx
0x180005577  cmp     edx, 6
0x18000557a  jg      short loc_1800055B6
0x18000557c  jz      short loc_1800055BD
0x18000557e  mov     ecx, edx
0x180005580  test    edx, edx
0x180005582  jz      short loc_1800055BD
0x180005584  sub     ecx, 1
0x180005587  jz      short loc_1800055BD
0x180005589  sub     ecx, 1
0x18000558c  jz      short loc_1800055BD
0x18000558e  sub     ecx, 1
0x180005591  jz      short loc_1800055BD
0x180005593  sub     ecx, 1
0x180005596  jz      short loc_1800055BD
0x180005598  cmp     ecx, 1
0x18000559b  jz      short loc_1800055BD
0x18000559d  mov     ecx, 57h ; 'W'; dwErrCode
0x1800055a2  call    cs:__imp_SetLastError
0x1800055a9  nop     dword ptr [rax+rax+00h]
0x1800055ae  xor     eax, eax
0x1800055b0  add     rsp, 28h
0x1800055b4  retn
0x1800055b6  mov     ecx, edx
0x1800055b8  sub     ecx, 7
0x1800055bb  jmp     short loc_180005582
0x1800055bd  test    r8, r8
0x1800055c0  jz      short loc_18000559D
0x1800055c2  mov     rcx, r9
0x1800055c5  add     rsp, 28h
0x1800055c9  jmp     ?GetILinkInfoData@@YAHPEBU_ilinkinfoW@@W4_linkinfodatatype@@PEAPEBX@Z; GetILinkInfoData(_ilinkinfoW const *,_linkinfodatatype,void const * *)
```
