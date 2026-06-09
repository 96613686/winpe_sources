# IASAttributeRelease

- ea: `0x18002af04`
- end: `0x18002af60`
- name: `IASAttributeRelease`
- size: `92`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `17`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012898`
- `0x180012c68`
- `0x180014478`
- `0x1800170c4`
- `0x180017544`
- `0x1800179a4`
- `0x1800181e8`
- `0x1800186b8`
- `0x180019340`
- `0x18001b4a0`
- `0x18001b898`
- `0x18001e4b8`
- `0x180028b74`
- `0x18002a398`
- `0x18002a4f8`
- `0x18002a6cc`
- `0x18002aa44`

## callees

- `0x18002af04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af58`

## pseudocode

```c
__int64 __fastcall IASAttributeRelease(LPVOID pv)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  void *v5; // rcx

  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv, 0xFFFFFFFF) == 1 )
  {
    v2 = *((_DWORD *)pv + 4) - 4;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          if ( v4 != 4 )
          {
LABEL_9:
            CoTaskMemFree(pv);
            return 0;
          }
          goto LABEL_7;
        }
      }
      else
      {
        CoTaskMemFree(*((LPVOID *)pv + 3));
      }
      v5 = (void *)*((_QWORD *)pv + 4);
      goto LABEL_8;
    }
LABEL_7:
    v5 = (void *)*((_QWORD *)pv + 3);
LABEL_8:
    CoTaskMemFree(v5);
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x18002af04  push    rbx
0x18002af06  sub     rsp, 20h
0x18002af0a  mov     rbx, rcx
0x18002af0d  test    rcx, rcx
0x18002af10  jz      short loc_18002AF46
0x18002af12  or      eax, 0FFFFFFFFh
0x18002af15  lock xadd [rcx], eax
0x18002af19  cmp     eax, 1
0x18002af1c  jnz     short loc_18002AF46
0x18002af1e  mov     ecx, [rcx+10h]
0x18002af21  sub     ecx, 4
0x18002af24  jz      short loc_18002AF33
0x18002af26  sub     ecx, eax
0x18002af28  jz      short loc_18002AF54
0x18002af2a  sub     ecx, eax
0x18002af2c  jz      short loc_18002AF4E
0x18002af2e  cmp     ecx, 4
0x18002af31  jnz     short loc_18002AF3D
0x18002af33  mov     rcx, [rbx+18h]; pv
0x18002af37  call    cs:__imp_CoTaskMemFree
0x18002af3d  mov     rcx, rbx; pv
0x18002af40  call    cs:__imp_CoTaskMemFree
0x18002af46  xor     eax, eax
0x18002af48  add     rsp, 20h
0x18002af4c  pop     rbx
0x18002af4d  retn
0x18002af4e  mov     rcx, [rbx+20h]
0x18002af52  jmp     short loc_18002AF37
0x18002af54  mov     rcx, [rbx+18h]; pv
0x18002af58  call    cs:__imp_CoTaskMemFree
0x18002af5e  jmp     short loc_18002AF4E
```
