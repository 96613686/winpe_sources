# IASAttributeRelease

- ea: `0x18000acf4`
- end: `0x18000ad50`
- name: `IASAttributeRelease`
- size: `92`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `89`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003254`
- `0x180003280`
- `0x180003364`
- `0x18000ad58`
- `0x18000b338`
- `0x18000b37c`
- `0x18000b484`
- `0x18000b614`
- `0x18000b648`
- `0x18000b82c`
- `0x18000bdf8`
- `0x18000c958`
- `0x18000cab4`
- `0x18000cd70`
- `0x18000ce58`
- `0x18000d154`
- `0x18000d630`
- `0x18000d794`
- `0x18000dbc0`
- `0x18000dfe0`
- `0x18000e2d0`
- `0x18000e538`
- `0x18000ea60`
- `0x18000f040`
- `0x18000f4e0`
- `0x18000f6e0`
- `0x18000fb84`
- `0x18000fdd4`
- `0x18000ff04`
- `0x18000ffa0`
- `0x180010058`
- `0x1800101c0`
- `0x180010274`
- `0x18001032c`
- `0x1800103e4`
- `0x180011190`
- `0x18001126c`
- `0x18001137c`
- `0x180011474`
- `0x180011514`
- `0x18001252c`
- `0x1800125fc`
- `0x18001299c`
- `0x1800133bc`
- `0x180013b70`
- `0x180013ce0`
- `0x180014098`
- `0x180014d20`
- `0x180015288`
- `0x1800152fc`

## callees

- `0x18000acf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad48`

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
0x18000acf4  push    rbx
0x18000acf6  sub     rsp, 20h
0x18000acfa  mov     rbx, rcx
0x18000acfd  test    rcx, rcx
0x18000ad00  jz      short loc_18000AD36
0x18000ad02  or      eax, 0FFFFFFFFh
0x18000ad05  lock xadd [rcx], eax
0x18000ad09  cmp     eax, 1
0x18000ad0c  jnz     short loc_18000AD36
0x18000ad0e  mov     ecx, [rcx+10h]
0x18000ad11  sub     ecx, 4
0x18000ad14  jz      short loc_18000AD23
0x18000ad16  sub     ecx, eax
0x18000ad18  jz      short loc_18000AD44
0x18000ad1a  sub     ecx, eax
0x18000ad1c  jz      short loc_18000AD3E
0x18000ad1e  cmp     ecx, 4
0x18000ad21  jnz     short loc_18000AD2D
0x18000ad23  mov     rcx, [rbx+18h]; pv
0x18000ad27  call    cs:__imp_CoTaskMemFree
0x18000ad2d  mov     rcx, rbx; pv
0x18000ad30  call    cs:__imp_CoTaskMemFree
0x18000ad36  xor     eax, eax
0x18000ad38  add     rsp, 20h
0x18000ad3c  pop     rbx
0x18000ad3d  retn
0x18000ad3e  mov     rcx, [rbx+20h]
0x18000ad42  jmp     short loc_18000AD27
0x18000ad44  mov     rcx, [rbx+18h]; pv
0x18000ad48  call    cs:__imp_CoTaskMemFree
0x18000ad4e  jmp     short loc_18000AD3E
```
