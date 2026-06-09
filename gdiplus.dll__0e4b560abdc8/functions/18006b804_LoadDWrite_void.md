# LoadDWrite(void)

- ea: `0x18006b804`
- end: `0x18006ba8b`
- name: `?LoadDWrite@@YAHXZ`
- size: `647`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006acdc`
- `0x18006af60`
- `0x180112a34`

## callees

- `0x18006b804`
- `0x18006ba94`
- `0x1800e5044`
- `0x1800e7e68`
- `0x1800e7e84`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b811`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b811`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b8c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b9e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b8c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b9e7`
- `DWrite!DWriteCreateFactory` at `0x18006b83b`
- `DWrite!DWriteCreateFactory` at `0x18006b83b`

## pseudocode

```c
__int64 LoadDWrite(void)
{
  GpFontCollectionFileLoader *v0; // rax
  GpFontCollectionStreamLoader *v1; // rax
  GpFontFileLoader *v3; // rax

  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  if ( Globals::g_DWriteFactory )
    goto LABEL_24;
  if ( (int)DWriteCreateFactory(0, &GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48, &Globals::g_DWriteFactory) >= 0 )
  {
    v0 = (GpFontCollectionFileLoader *)GpMallocEx(16, 0);
    if ( v0 )
    {
      Globals::g_GpFontCollectionFileLoader = GpFontCollectionFileLoader::GpFontCollectionFileLoader(v0);
      if ( Globals::g_GpFontCollectionFileLoader )
      {
        v1 = (GpFontCollectionStreamLoader *)GpMallocEx(16, 0);
        if ( !v1 )
          goto LABEL_6;
        Globals::g_GpFontCollectionStreamLoader = GpFontCollectionStreamLoader::GpFontCollectionStreamLoader(v1);
        if ( !Globals::g_GpFontCollectionStreamLoader )
          goto LABEL_7;
        v3 = (GpFontFileLoader *)GpMallocEx(16, 0);
        if ( v3 )
        {
          Globals::g_GpFontFileLoader = GpFontFileLoader::GpFontFileLoader(v3);
          if ( Globals::g_GpFontFileLoader
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteFontFileLoader *))(*(_QWORD *)Globals::g_DWriteFactory
                                                                                              + 104LL))(
                 Globals::g_DWriteFactory,
                 Globals::g_GpFontFileLoader) >= 0
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_DWriteFactory + 40LL))(
                 Globals::g_DWriteFactory,
                 Globals::g_GpFontCollectionFileLoader) >= 0
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_DWriteFactory + 40LL))(
                 Globals::g_DWriteFactory,
                 Globals::g_GpFontCollectionStreamLoader) >= 0
            && (*(int (__fastcall **)(struct IDWriteFactory *, struct IDWriteTextAnalyzer **))(*(_QWORD *)Globals::g_DWriteFactory
                                                                                             + 168LL))(
                 Globals::g_DWriteFactory,
                 &Globals::g_DWriteTextAnalyzer) >= 0 )
          {
LABEL_24:
            LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
            return 1;
          }
        }
        else
        {
          Globals::g_GpFontFileLoader = 0;
        }
      }
    }
    else
    {
      Globals::g_GpFontCollectionFileLoader = 0;
    }
  }
  if ( !Globals::g_GpFontCollectionStreamLoader )
    goto LABEL_7;
  (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
  (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionStreamLoader
                                                               + 16LL))(Globals::g_GpFontCollectionStreamLoader);
LABEL_6:
  Globals::g_GpFontCollectionStreamLoader = 0;
LABEL_7:
  if ( Globals::g_GpFontCollectionFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionFileLoader
                                                                 + 16LL))(Globals::g_GpFontCollectionFileLoader);
    Globals::g_GpFontCollectionFileLoader = 0;
  }
  if ( Globals::g_GpFontFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 112LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontFileLoader *))(*(_QWORD *)Globals::g_GpFontFileLoader + 16LL))(Globals::g_GpFontFileLoader);
    Globals::g_GpFontFileLoader = 0;
  }
  if ( Globals::g_DWriteFactory )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 16LL))(Globals::g_DWriteFactory);
    Globals::g_DWriteFactory = 0;
  }
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return 0;
}

```

## disassembly

```asm
0x18006b804  push    rdi
0x18006b806  sub     rsp, 20h
0x18006b80a  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006b811  call    cs:__imp_EnterCriticalSection
0x18006b818  nop     dword ptr [rax+rax+00h]
0x18006b81d  cmp     cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA, 0; IDWriteFactory * Globals::g_DWriteFactory
0x18006b825  jnz     loc_18006B9E0
0x18006b82b  lea     r8, ?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b832  xor     ecx, ecx
0x18006b834  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x18006b83b  call    cs:__imp_DWriteCreateFactory
0x18006b842  nop     dword ptr [rax+rax+00h]
0x18006b847  test    eax, eax
0x18006b849  js      loc_18006B8E0
0x18006b84f  xor     edx, edx
0x18006b851  lea     edi, [rdx+10h]
0x18006b854  mov     ecx, edi
0x18006b856  call    GpMallocEx
0x18006b85b  test    rax, rax
0x18006b85e  jz      short loc_18006B8D8
0x18006b860  mov     rcx, rax; this
0x18006b863  call    ??0GpFontCollectionFileLoader@@QEAA@XZ; GpFontCollectionFileLoader::GpFontCollectionFileLoader(void)
0x18006b868  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rax; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18006b86f  test    rax, rax
0x18006b872  jz      short loc_18006B8E0
0x18006b874  xor     edx, edx
0x18006b876  mov     ecx, edi
0x18006b878  call    GpMallocEx
0x18006b87d  test    rax, rax
0x18006b880  jnz     loc_18006B917
0x18006b886  and     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18006b88e  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18006b895  test    rdx, rdx
0x18006b898  jnz     loc_18006BA0C
0x18006b89e  mov     rdx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18006b8a5  test    rdx, rdx
0x18006b8a8  jnz     loc_18006BA3F
0x18006b8ae  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b8b5  test    rcx, rcx
0x18006b8b8  jnz     loc_18006BA72
0x18006b8be  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006b8c5  call    cs:__imp_LeaveCriticalSection
0x18006b8cc  nop     dword ptr [rax+rax+00h]
0x18006b8d1  xor     eax, eax
0x18006b8d3  jmp     loc_18006B9F8
0x18006b8d8  and     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18006b8e0  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18006b8e7  test    rdx, rdx
0x18006b8ea  jz      short loc_18006B88E
0x18006b8ec  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b8f3  mov     rax, [rcx]
0x18006b8f6  mov     rax, [rax+30h]
0x18006b8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8ff  mov     rcx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18006b906  mov     rax, [rcx]
0x18006b909  mov     rax, [rax+10h]
0x18006b90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b912  jmp     loc_18006B886
0x18006b917  mov     rcx, rax; this
0x18006b91a  call    ??0GpFontCollectionStreamLoader@@QEAA@XZ; GpFontCollectionStreamLoader::GpFontCollectionStreamLoader(void)
0x18006b91f  mov     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rax; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18006b926  test    rax, rax
0x18006b929  jz      loc_18006B88E
0x18006b92f  xor     edx, edx
0x18006b931  mov     rcx, rdi
0x18006b934  call    GpMallocEx
0x18006b939  test    rax, rax
0x18006b93c  jz      loc_18006B9FF
0x18006b942  mov     rcx, rax; this
0x18006b945  call    ??0GpFontFileLoader@@QEAA@XZ; GpFontFileLoader::GpFontFileLoader(void)
0x18006b94a  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, rax; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18006b951  mov     rdx, rax
0x18006b954  test    rax, rax
0x18006b957  jz      short loc_18006B8E0
0x18006b959  mov     r8, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b960  mov     rcx, [r8]
0x18006b963  mov     rax, [rcx+68h]
0x18006b967  mov     rcx, r8
0x18006b96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b96f  test    eax, eax
0x18006b971  js      loc_18006B8E0
0x18006b977  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b97e  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18006b985  mov     rax, [rcx]
0x18006b988  mov     rax, [rax+28h]
0x18006b98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b991  test    eax, eax
0x18006b993  js      loc_18006B8E0
0x18006b999  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b9a0  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18006b9a7  mov     rax, [rcx]
0x18006b9aa  mov     rax, [rax+28h]
0x18006b9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9b3  test    eax, eax
0x18006b9b5  js      loc_18006B8E0
0x18006b9bb  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006b9c2  lea     rdx, ?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x18006b9c9  mov     rax, [rcx]
0x18006b9cc  mov     rax, [rax+0A8h]
0x18006b9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9d8  test    eax, eax
0x18006b9da  js      loc_18006B8E0
0x18006b9e0  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006b9e7  call    cs:__imp_LeaveCriticalSection
0x18006b9ee  nop     dword ptr [rax+rax+00h]
0x18006b9f3  mov     eax, 1
0x18006b9f8  add     rsp, 20h
0x18006b9fc  pop     rdi
0x18006b9fd  retn
0x18006b9ff  and     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, 0; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18006ba07  jmp     loc_18006B8E0
0x18006ba0c  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006ba13  mov     rax, [rcx]
0x18006ba16  mov     rax, [rax+30h]
0x18006ba1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba1f  mov     rcx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18006ba26  mov     rax, [rcx]
0x18006ba29  mov     rax, [rax+10h]
0x18006ba2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba32  and     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18006ba3a  jmp     loc_18006B89E
0x18006ba3f  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18006ba46  mov     rax, [rcx]
0x18006ba49  mov     rax, [rax+70h]
0x18006ba4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba52  mov     rcx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18006ba59  mov     rax, [rcx]
0x18006ba5c  mov     rax, [rax+10h]
0x18006ba60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba65  and     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, 0; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18006ba6d  jmp     loc_18006B8AE
0x18006ba72  mov     rax, [rcx]
0x18006ba75  mov     rax, [rax+10h]
0x18006ba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba7e  and     cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA, 0; IDWriteFactory * Globals::g_DWriteFactory
0x18006ba86  jmp     loc_18006B8BE
```
