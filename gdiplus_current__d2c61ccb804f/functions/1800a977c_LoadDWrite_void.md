# LoadDWrite(void)

- ea: `0x1800a977c`
- end: `0x1800a9a13`
- name: `?LoadDWrite@@YAHXZ`
- size: `663`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180088638`
- `0x1800a8d8c`
- `0x1801285c0`

## callees

- `0x180063cd8`
- `0x1800a977c`
- `0x1800a9a1c`
- `0x1800a9a38`
- `0x1800f89f4`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a9789`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a9789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9938`
- `DWrite!DWriteCreateFactory` at `0x1800a97b3`
- `DWrite!DWriteCreateFactory` at `0x1800a97b3`

## pseudocode

```c
__int64 LoadDWrite(void)
{
  GpFontCollectionFileLoader *v0; // rax
  GpFontCollectionStreamLoader *v1; // rax
  GpFontFileLoader *v3; // rax

  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  if ( Globals::g_DWriteFactory )
    goto LABEL_23;
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
          goto LABEL_9;
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
LABEL_23:
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
    goto LABEL_9;
  (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
  (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionStreamLoader
                                                               + 16LL))(Globals::g_GpFontCollectionStreamLoader);
LABEL_6:
  Globals::g_GpFontCollectionStreamLoader = 0;
LABEL_9:
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
0x1800a977c  push    rdi
0x1800a977e  sub     rsp, 20h
0x1800a9782  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a9789  call    cs:__imp_EnterCriticalSection
0x1800a9790  nop     dword ptr [rax+rax+00h]
0x1800a9795  cmp     cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA, 0; IDWriteFactory * Globals::g_DWriteFactory
0x1800a979d  jnz     loc_1800A9931
0x1800a97a3  lea     r8, ?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a97aa  xor     ecx, ecx
0x1800a97ac  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x1800a97b3  call    cs:__imp_DWriteCreateFactory
0x1800a97ba  nop     dword ptr [rax+rax+00h]
0x1800a97bf  test    eax, eax
0x1800a97c1  js      short loc_1800A980E
0x1800a97c3  xor     edx, edx
0x1800a97c5  lea     edi, [rdx+10h]
0x1800a97c8  mov     ecx, edi
0x1800a97ca  call    GpMallocEx
0x1800a97cf  test    rax, rax
0x1800a97d2  jz      short loc_1800A9803
0x1800a97d4  mov     rcx, rax; this
0x1800a97d7  call    ??0GpFontCollectionFileLoader@@QEAA@XZ; GpFontCollectionFileLoader::GpFontCollectionFileLoader(void)
0x1800a97dc  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rax; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800a97e3  test    rax, rax
0x1800a97e6  jz      short loc_1800A980E
0x1800a97e8  xor     edx, edx
0x1800a97ea  mov     ecx, edi
0x1800a97ec  call    GpMallocEx
0x1800a97f1  test    rax, rax
0x1800a97f4  jnz     short loc_1800A9868
0x1800a97f6  mov     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800a9801  jmp     short loc_1800A981E
0x1800a9803  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800a980e  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800a9815  test    rdx, rdx
0x1800a9818  jnz     loc_1800A9960
0x1800a981e  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800a9825  test    rdx, rdx
0x1800a9828  jnz     loc_1800A998B
0x1800a982e  mov     rdx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800a9835  test    rdx, rdx
0x1800a9838  jnz     loc_1800A99C1
0x1800a983e  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a9845  test    rcx, rcx
0x1800a9848  jnz     loc_1800A99F7
0x1800a984e  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a9855  call    cs:__imp_LeaveCriticalSection
0x1800a985c  nop     dword ptr [rax+rax+00h]
0x1800a9861  xor     eax, eax
0x1800a9863  jmp     loc_1800A9949
0x1800a9868  mov     rcx, rax; this
0x1800a986b  call    ??0GpFontCollectionStreamLoader@@QEAA@XZ; GpFontCollectionStreamLoader::GpFontCollectionStreamLoader(void)
0x1800a9870  mov     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rax; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800a9877  test    rax, rax
0x1800a987a  jz      short loc_1800A981E
0x1800a987c  xor     edx, edx
0x1800a987e  mov     rcx, rdi
0x1800a9881  call    GpMallocEx
0x1800a9886  test    rax, rax
0x1800a9889  jz      loc_1800A9950
0x1800a988f  mov     rcx, rax; this
0x1800a9892  call    ??0GpFontFileLoader@@QEAA@XZ; GpFontFileLoader::GpFontFileLoader(void)
0x1800a9897  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, rax; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800a989e  mov     rdx, rax
0x1800a98a1  test    rax, rax
0x1800a98a4  jz      loc_1800A980E
0x1800a98aa  mov     r8, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a98b1  mov     rcx, [r8]
0x1800a98b4  mov     rax, [rcx+68h]
0x1800a98b8  mov     rcx, r8
0x1800a98bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98c0  test    eax, eax
0x1800a98c2  js      loc_1800A980E
0x1800a98c8  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a98cf  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800a98d6  mov     rax, [rcx]
0x1800a98d9  mov     rax, [rax+28h]
0x1800a98dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98e2  test    eax, eax
0x1800a98e4  js      loc_1800A980E
0x1800a98ea  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a98f1  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800a98f8  mov     rax, [rcx]
0x1800a98fb  mov     rax, [rax+28h]
0x1800a98ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9904  test    eax, eax
0x1800a9906  js      loc_1800A980E
0x1800a990c  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a9913  lea     rdx, ?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x1800a991a  mov     rax, [rcx]
0x1800a991d  mov     rax, [rax+0A8h]
0x1800a9924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9929  test    eax, eax
0x1800a992b  js      loc_1800A980E
0x1800a9931  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a9938  call    cs:__imp_LeaveCriticalSection
0x1800a993f  nop     dword ptr [rax+rax+00h]
0x1800a9944  mov     eax, 1
0x1800a9949  add     rsp, 20h
0x1800a994d  pop     rdi
0x1800a994e  retn
0x1800a9950  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, 0; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800a995b  jmp     loc_1800A980E
0x1800a9960  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a9967  mov     rax, [rcx]
0x1800a996a  mov     rax, [rax+30h]
0x1800a996e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9973  mov     rcx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800a997a  mov     rax, [rcx]
0x1800a997d  mov     rax, [rax+10h]
0x1800a9981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9986  jmp     loc_1800A97F6
0x1800a998b  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a9992  mov     rax, [rcx]
0x1800a9995  mov     rax, [rax+30h]
0x1800a9999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a999e  mov     rcx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800a99a5  mov     rax, [rcx]
0x1800a99a8  mov     rax, [rax+10h]
0x1800a99ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99b1  mov     cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, 0; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800a99bc  jmp     loc_1800A982E
0x1800a99c1  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800a99c8  mov     rax, [rcx]
0x1800a99cb  mov     rax, [rax+70h]
0x1800a99cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99d4  mov     rcx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800a99db  mov     rax, [rcx]
0x1800a99de  mov     rax, [rax+10h]
0x1800a99e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99e7  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, 0; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800a99f2  jmp     loc_1800A983E
0x1800a99f7  mov     rax, [rcx]
0x1800a99fa  mov     rax, [rax+10h]
0x1800a99fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a03  mov     cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA, 0; IDWriteFactory * Globals::g_DWriteFactory
0x1800a9a0e  jmp     loc_1800A984E
```
