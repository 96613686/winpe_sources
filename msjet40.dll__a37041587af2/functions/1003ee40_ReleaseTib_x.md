# ReleaseTib(x)

- ea: `0x1003ee40`
- end: `0x1003f023`
- name: `_ReleaseTib@4`
- size: `483`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1001ab50`
- `0x10026dd0`
- `0x10026ec0`
- `0x100287e0`

## callees

- `0x1003ee40`
- `0x10050190`
- `0x10122b8a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ee6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ee8c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ee6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ee8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1003f00e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1003f00e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1003efab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1003efab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1003f019`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1003f019`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003efc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003efde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003eff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003efc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003efde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003eff4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1003efba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1003efba`

## pseudocode

```c
void __fastcall ReleaseTib(unsigned int a1)
{
  void **v2; // ebx
  int v3; // ecx
  int v4; // eax
  int *v5; // edx
  void *v6; // edx
  void *v7; // edx
  int v8; // eax

  if ( rgtib && a1 <= 0x3F )
  {
    v2 = (void **)((char *)rgtib + 2316 * a1);
    if ( v2[569] )
    {
      _free(v2[569]);
      v2[569] = 0;
    }
    if ( v2[262] )
      _free(v2[262]);
    v3 = dword_1012C324;
    if ( a1 == dword_1012C324 )
    {
      v3 = rgtibNext[a1];
      dword_1012C324 = v3;
    }
    else
    {
      v4 = dword_1012C324;
      if ( dword_1012C324 != -1 )
      {
        while ( 1 )
        {
          v5 = &rgtibNext[v4];
          v4 = *v5;
          if ( *v5 == a1 )
            break;
          if ( v4 == -1 )
            goto LABEL_14;
        }
        *v5 = rgtibNext[a1];
      }
    }
LABEL_14:
    v6 = v2[574];
    if ( v6 )
    {
      (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v6 + 8))(*(_DWORD *)(*(_DWORD *)v6 + 8), v2[574]);
      v3 = dword_1012C324;
    }
    v7 = v2[575];
    if ( v7 )
    {
      (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v7 + 8))(*(_DWORD *)(*(_DWORD *)v7 + 8), v2[575]);
      v3 = dword_1012C324;
    }
    v8 = dword_1012C328;
    v2[263] = 0;
    rgtibNext[a1] = v8;
    dword_1012C328 = a1;
    if ( v3 == -1 )
    {
      if ( g_pIJetESBSTRTracker )
      {
        (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)g_pIJetESBSTRTracker + 8))(
          *(_DWORD *)(*(_DWORD *)g_pIJetESBSTRTracker + 8),
          g_pIJetESBSTRTracker);
        g_pIJetESBSTRTracker = 0;
      }
      if ( g_pIJetES )
      {
        (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)g_pIJetES + 8))(
          *(_DWORD *)(*(_DWORD *)g_pIJetES + 8),
          g_pIJetES);
        g_pIJetES = 0;
      }
      if ( dword_10131188 )
      {
        PostCOMCallThreadRequest(999, 99);
        while ( WaitForSingleObject(hObject, 0x1F4u) == 258 )
          Sleep(0);
        CloseHandle(hObject);
        hObject = 0;
        CloseHandle(hHandle);
        hHandle = 0;
        CloseHandle(pHandles);
        pHandles = 0;
        if ( hLibModule )
          FreeLibrary(hLibModule);
        DeleteCriticalSection(&CriticalSection);
      }
    }
  }
}

```

## disassembly

```asm
0x1003ee40  mov     eax, _rgtib
0x1003ee45  push    edi
0x1003ee46  mov     edi, ecx
0x1003ee48  test    eax, eax
0x1003ee4a  jz      loc_1003F021
0x1003ee50  cmp     edi, 3Fh ; '?'
0x1003ee53  ja      loc_1003F021
0x1003ee59  push    ebx
0x1003ee5a  imul    ebx, edi, 90Ch
0x1003ee60  push    esi; unsigned int
0x1003ee61  add     ebx, eax
0x1003ee63  mov     eax, [ebx+8E4h]
0x1003ee69  test    eax, eax
0x1003ee6b  jz      short loc_1003EE81
0x1003ee6d  push    eax; Block
0x1003ee6e  call    ds:__imp__free
0x1003ee74  add     esp, 4
0x1003ee77  mov     dword ptr [ebx+8E4h], 0
0x1003ee81  mov     eax, [ebx+418h]
0x1003ee87  test    eax, eax
0x1003ee89  jz      short loc_1003EE95
0x1003ee8b  push    eax; Block
0x1003ee8c  call    ds:__imp__free
0x1003ee92  add     esp, 4
0x1003ee95  mov     ecx, dword_1012C324
0x1003ee9b  cmp     edi, ecx
0x1003ee9d  jnz     short loc_1003EEAE
0x1003ee9f  mov     ecx, _rgtibNext[edi*4]
0x1003eea6  mov     dword_1012C324, ecx
0x1003eeac  jmp     short loc_1003EED2
0x1003eeae  mov     eax, ecx
0x1003eeb0  cmp     eax, 0FFFFFFFFh
0x1003eeb3  jz      short loc_1003EED2
0x1003eeb5  lea     edx, _rgtibNext[eax*4]
0x1003eebc  mov     eax, [edx]
0x1003eebe  cmp     eax, edi
0x1003eec0  jz      short loc_1003EEC9
0x1003eec2  cmp     eax, 0FFFFFFFFh
0x1003eec5  jnz     short loc_1003EEB5
0x1003eec7  jmp     short loc_1003EED2
0x1003eec9  mov     eax, _rgtibNext[edi*4]
0x1003eed0  mov     [edx], eax
0x1003eed2  mov     edx, [ebx+8F8h]
0x1003eed8  test    edx, edx
0x1003eeda  jz      short loc_1003EEF2
0x1003eedc  mov     eax, [edx]
0x1003eede  push    edx; void *
0x1003eedf  mov     esi, [eax+8]
0x1003eee2  mov     ecx, esi
0x1003eee4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003eeea  call    esi
0x1003eeec  mov     ecx, dword_1012C324
0x1003eef2  mov     edx, [ebx+8FCh]
0x1003eef8  test    edx, edx
0x1003eefa  jz      short loc_1003EF12
0x1003eefc  mov     eax, [edx]
0x1003eefe  push    edx; void *
0x1003eeff  mov     esi, [eax+8]
0x1003ef02  mov     ecx, esi
0x1003ef04  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ef0a  call    esi
0x1003ef0c  mov     ecx, dword_1012C324
0x1003ef12  mov     eax, dword_1012C328
0x1003ef17  mov     dword ptr [ebx+41Ch], 0
0x1003ef21  mov     _rgtibNext[edi*4], eax
0x1003ef28  mov     dword_1012C328, edi
0x1003ef2e  cmp     ecx, 0FFFFFFFFh
0x1003ef31  jnz     loc_1003F01F
0x1003ef37  mov     ecx, ?g_pIJetESBSTRTracker@@3PAUIJetESBSTRTracker@@A; IJetESBSTRTracker * g_pIJetESBSTRTracker
0x1003ef3d  test    ecx, ecx
0x1003ef3f  jz      short loc_1003EF5B
0x1003ef41  mov     eax, [ecx]
0x1003ef43  push    ecx; void *
0x1003ef44  mov     esi, [eax+8]
0x1003ef47  mov     ecx, esi
0x1003ef49  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ef4f  call    esi
0x1003ef51  mov     ?g_pIJetESBSTRTracker@@3PAUIJetESBSTRTracker@@A, 0; IJetESBSTRTracker * g_pIJetESBSTRTracker
0x1003ef5b  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x1003ef61  test    ecx, ecx
0x1003ef63  jz      short loc_1003EF7F
0x1003ef65  mov     eax, [ecx]
0x1003ef67  push    ecx; void *
0x1003ef68  mov     esi, [eax+8]
0x1003ef6b  mov     ecx, esi
0x1003ef6d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ef73  call    esi
0x1003ef75  mov     ?g_pIJetES@@3PAUIJetES@@A, 0; IJetES * g_pIJetES
0x1003ef7f  cmp     dword_10131188, 0
0x1003ef86  jz      loc_1003F01F
0x1003ef8c  push    63h ; 'c'
0x1003ef8e  push    3E7h
0x1003ef93  call    ?PostCOMCallThreadRequest@@YAJW4etCOMCall@@ZZ; PostCOMCallThreadRequest(etCOMCall,...)
0x1003ef98  add     esp, 8
0x1003ef9b  nop     dword ptr [eax+eax+00h]
0x1003efa0  push    1F4h; dwMilliseconds
0x1003efa5  push    hObject; hHandle
0x1003efab  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1003efb1  cmp     eax, 102h
0x1003efb6  jnz     short loc_1003EFC2
0x1003efb8  push    0; dwMilliseconds
0x1003efba  call    ds:__imp__Sleep@4; Sleep(x)
0x1003efc0  jmp     short loc_1003EFA0
0x1003efc2  push    hObject; hObject
0x1003efc8  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003efce  push    hHandle; hObject
0x1003efd4  mov     hObject, 0
0x1003efde  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003efe4  push    pHandles; hObject
0x1003efea  mov     hHandle, 0
0x1003eff4  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003effa  mov     eax, hLibModule
0x1003efff  mov     pHandles, 0
0x1003f009  test    eax, eax
0x1003f00b  jz      short loc_1003F014
0x1003f00d  push    eax; hLibModule
0x1003f00e  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1003f014  push    offset CriticalSection; lpCriticalSection
0x1003f019  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1003f01f  pop     esi
0x1003f020  pop     ebx
0x1003f021  pop     edi
0x1003f022  retn
```
