# ATL::CComAggObject<CMSDiscRecorderObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800071f0`
- end: `0x180007253`
- name: `?QueryInterface@?$CComAggObject@VCMSDiscRecorderObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002f84`
- `0x1800071f0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSDiscRecorderObj>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMSDiscRecorderObj::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800071f0  push    rbx
0x1800071f2  sub     rsp, 20h
0x1800071f6  xor     ebx, ebx
0x1800071f8  test    r8, r8
0x1800071fb  jnz     short loc_180007204
0x1800071fd  mov     eax, 80004003h
0x180007202  jmp     short loc_18000724D
0x180007204  mov     [r8], rbx
0x180007207  cmp     [rdx], ebx
0x180007209  jnz     short loc_180007233
0x18000720b  cmp     [rdx+4], ebx
0x18000720e  jnz     short loc_180007233
0x180007210  cmp     dword ptr [rdx+8], 0C0h
0x180007217  jnz     short loc_180007233
0x180007219  cmp     dword ptr [rdx+0Ch], 46000000h
0x180007220  jnz     short loc_180007233
0x180007222  mov     [r8], rcx
0x180007225  mov     rax, [rcx]
0x180007228  mov     rax, [rax+8]
0x18000722c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007231  jmp     short loc_18000724B
0x180007233  mov     r9, r8; void **
0x180007236  add     rcx, 18h; void *
0x18000723a  mov     r8, rdx; struct _GUID *
0x18000723d  lea     rdx, ?_entries@?1??_GetEntries@CMSDiscRecorderObj@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180007244  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180007249  mov     ebx, eax
0x18000724b  mov     eax, ebx
0x18000724d  add     rsp, 20h
0x180007251  pop     rbx
0x180007252  retn
```
