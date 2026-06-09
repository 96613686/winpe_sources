# ReleaseTib(x)

- ea: `0x1003ecb0`
- end: `0x1003ee93`
- name: `_ReleaseTib@4`
- size: `483`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1001aa00`
- `0x10026c70`
- `0x10026d60`
- `0x10028610`

## callees

- `0x1003ecb0`
- `0x10050000`
- `0x101229da`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ecde`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ecfc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ecde`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ecfc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1003ee7e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1003ee7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1003ee1b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1003ee1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1003ee89`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1003ee89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003ee38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003ee4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003ee64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003ee38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003ee4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1003ee64`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1003ee2a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1003ee2a`

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
    v3 = dword_1012C2E4;
    if ( a1 == dword_1012C2E4 )
    {
      v3 = rgtibNext[a1];
      dword_1012C2E4 = v3;
    }
    else
    {
      v4 = dword_1012C2E4;
      if ( dword_1012C2E4 != -1 )
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
      v3 = dword_1012C2E4;
    }
    v7 = v2[575];
    if ( v7 )
    {
      (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v7 + 8))(*(_DWORD *)(*(_DWORD *)v7 + 8), v2[575]);
      v3 = dword_1012C2E4;
    }
    v8 = dword_1012C2E8;
    v2[263] = 0;
    rgtibNext[a1] = v8;
    dword_1012C2E8 = a1;
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
      if ( dword_101310D8 )
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
0x1003ecb0  mov     eax, _rgtib
0x1003ecb5  push    edi
0x1003ecb6  mov     edi, ecx
0x1003ecb8  test    eax, eax
0x1003ecba  jz      loc_1003EE91
0x1003ecc0  cmp     edi, 3Fh ; '?'
0x1003ecc3  ja      loc_1003EE91
0x1003ecc9  push    ebx
0x1003ecca  imul    ebx, edi, 90Ch
0x1003ecd0  push    esi; unsigned int
0x1003ecd1  add     ebx, eax
0x1003ecd3  mov     eax, [ebx+8E4h]
0x1003ecd9  test    eax, eax
0x1003ecdb  jz      short loc_1003ECF1
0x1003ecdd  push    eax; Block
0x1003ecde  call    ds:__imp__free
0x1003ece4  add     esp, 4
0x1003ece7  mov     dword ptr [ebx+8E4h], 0
0x1003ecf1  mov     eax, [ebx+418h]
0x1003ecf7  test    eax, eax
0x1003ecf9  jz      short loc_1003ED05
0x1003ecfb  push    eax; Block
0x1003ecfc  call    ds:__imp__free
0x1003ed02  add     esp, 4
0x1003ed05  mov     ecx, dword_1012C2E4
0x1003ed0b  cmp     edi, ecx
0x1003ed0d  jnz     short loc_1003ED1E
0x1003ed0f  mov     ecx, _rgtibNext[edi*4]
0x1003ed16  mov     dword_1012C2E4, ecx
0x1003ed1c  jmp     short loc_1003ED42
0x1003ed1e  mov     eax, ecx
0x1003ed20  cmp     eax, 0FFFFFFFFh
0x1003ed23  jz      short loc_1003ED42
0x1003ed25  lea     edx, _rgtibNext[eax*4]
0x1003ed2c  mov     eax, [edx]
0x1003ed2e  cmp     eax, edi
0x1003ed30  jz      short loc_1003ED39
0x1003ed32  cmp     eax, 0FFFFFFFFh
0x1003ed35  jnz     short loc_1003ED25
0x1003ed37  jmp     short loc_1003ED42
0x1003ed39  mov     eax, _rgtibNext[edi*4]
0x1003ed40  mov     [edx], eax
0x1003ed42  mov     edx, [ebx+8F8h]
0x1003ed48  test    edx, edx
0x1003ed4a  jz      short loc_1003ED62
0x1003ed4c  mov     eax, [edx]
0x1003ed4e  push    edx; void *
0x1003ed4f  mov     esi, [eax+8]
0x1003ed52  mov     ecx, esi
0x1003ed54  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ed5a  call    esi
0x1003ed5c  mov     ecx, dword_1012C2E4
0x1003ed62  mov     edx, [ebx+8FCh]
0x1003ed68  test    edx, edx
0x1003ed6a  jz      short loc_1003ED82
0x1003ed6c  mov     eax, [edx]
0x1003ed6e  push    edx; void *
0x1003ed6f  mov     esi, [eax+8]
0x1003ed72  mov     ecx, esi
0x1003ed74  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ed7a  call    esi
0x1003ed7c  mov     ecx, dword_1012C2E4
0x1003ed82  mov     eax, dword_1012C2E8
0x1003ed87  mov     dword ptr [ebx+41Ch], 0
0x1003ed91  mov     _rgtibNext[edi*4], eax
0x1003ed98  mov     dword_1012C2E8, edi
0x1003ed9e  cmp     ecx, 0FFFFFFFFh
0x1003eda1  jnz     loc_1003EE8F
0x1003eda7  mov     ecx, ?g_pIJetESBSTRTracker@@3PAUIJetESBSTRTracker@@A; IJetESBSTRTracker * g_pIJetESBSTRTracker
0x1003edad  test    ecx, ecx
0x1003edaf  jz      short loc_1003EDCB
0x1003edb1  mov     eax, [ecx]
0x1003edb3  push    ecx; void *
0x1003edb4  mov     esi, [eax+8]
0x1003edb7  mov     ecx, esi
0x1003edb9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003edbf  call    esi
0x1003edc1  mov     ?g_pIJetESBSTRTracker@@3PAUIJetESBSTRTracker@@A, 0; IJetESBSTRTracker * g_pIJetESBSTRTracker
0x1003edcb  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x1003edd1  test    ecx, ecx
0x1003edd3  jz      short loc_1003EDEF
0x1003edd5  mov     eax, [ecx]
0x1003edd7  push    ecx; void *
0x1003edd8  mov     esi, [eax+8]
0x1003eddb  mov     ecx, esi
0x1003eddd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ede3  call    esi
0x1003ede5  mov     ?g_pIJetES@@3PAUIJetES@@A, 0; IJetES * g_pIJetES
0x1003edef  cmp     dword_101310D8, 0
0x1003edf6  jz      loc_1003EE8F
0x1003edfc  push    63h ; 'c'
0x1003edfe  push    3E7h
0x1003ee03  call    ?PostCOMCallThreadRequest@@YAJW4etCOMCall@@ZZ; PostCOMCallThreadRequest(etCOMCall,...)
0x1003ee08  add     esp, 8
0x1003ee0b  nop     dword ptr [eax+eax+00h]
0x1003ee10  push    1F4h; dwMilliseconds
0x1003ee15  push    hObject; hHandle
0x1003ee1b  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1003ee21  cmp     eax, 102h
0x1003ee26  jnz     short loc_1003EE32
0x1003ee28  push    0; dwMilliseconds
0x1003ee2a  call    ds:__imp__Sleep@4; Sleep(x)
0x1003ee30  jmp     short loc_1003EE10
0x1003ee32  push    hObject; hObject
0x1003ee38  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003ee3e  push    hHandle; hObject
0x1003ee44  mov     hObject, 0
0x1003ee4e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003ee54  push    pHandles; hObject
0x1003ee5a  mov     hHandle, 0
0x1003ee64  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003ee6a  mov     eax, hLibModule
0x1003ee6f  mov     pHandles, 0
0x1003ee79  test    eax, eax
0x1003ee7b  jz      short loc_1003EE84
0x1003ee7d  push    eax; hLibModule
0x1003ee7e  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1003ee84  push    offset CriticalSection; lpCriticalSection
0x1003ee89  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1003ee8f  pop     esi
0x1003ee90  pop     ebx
0x1003ee91  pop     edi
0x1003ee92  retn
```
