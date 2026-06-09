# CEncryptionProgressDialog::_Initialize(void)

- ea: `0x1800301c8`
- end: `0x180030300`
- name: `?_Initialize@CEncryptionProgressDialog@@AEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(CEncryptionProgressDialog *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002f840`

## callees

- `0x180004070`
- `0x180008a7c`
- `0x1800300e0`
- `0x1800301c8`
- `0x18004c636`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003028b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800302b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003028b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800302b2`

## pseudocode

```c
__int64 __fastcall CEncryptionProgressDialog::_Initialize(CEncryptionProgressDialog *this)
{
  int Error; // edi
  int v3; // edx
  HANDLE EventW; // rax
  HANDLE v5; // rax
  HDSA v6; // rax

  Error = 0;
  memset_0((char *)this + 60, 0, 0xA0u);
  v3 = *((_DWORD *)this + 12);
  *((_QWORD *)this + 8) = *((_QWORD *)this + 3);
  *((_QWORD *)this + 9) = g_hInstance;
  *((_DWORD *)this + 15) = 160;
  *((_DWORD *)this + 20) = 7176;
  *((_DWORD *)this + 21) = 8;
  *((_DWORD *)this + 33) = 2;
  *((_QWORD *)this + 11) = 45;
  *((_QWORD *)this + 13) = (-(__int64)(v3 != 0) & 0xFFFFFFFFFFFFFFF7uLL) + 4410;
  *((_QWORD *)this + 26) = this;
  *((_QWORD *)this + 14) = (-(__int64)(v3 != 0) & 0xFFFFFFFFFFFFFFF7uLL) + 4411;
  *((_QWORD *)this + 24) = L"    ";
  *((_QWORD *)this + 25) = CEncryptionProgressDialog::_ProgressCallbackProc;
  CEncryptionProgressDialog::_InitErrorConfigInfo(this);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 54) = EventW;
  if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v5 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 53) = v5;
    if ( v5 || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      v6 = DSA_Create(4, 10);
      *((_QWORD *)this + 58) = v6;
      if ( !v6 )
        return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800301c8  mov     [rsp+arg_0], rbx
0x1800301cd  mov     [rsp+arg_8], rsi
0x1800301d2  push    rdi
0x1800301d3  sub     rsp, 20h
0x1800301d7  mov     rsi, rcx
0x1800301da  xor     edx, edx; Val
0x1800301dc  add     rcx, 3Ch ; '<'; void *
0x1800301e0  mov     r8d, 0A0h; Size
0x1800301e6  xor     edi, edi
0x1800301e8  call    memset_0
0x1800301ed  mov     rax, [rsi+18h]
0x1800301f1  mov     edx, [rsi+30h]
0x1800301f4  mov     [rsi+40h], rax
0x1800301f8  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800301ff  mov     [rsi+48h], rax
0x180030203  mov     eax, edx
0x180030205  neg     eax
0x180030207  mov     dword ptr [rsi+3Ch], 0A0h
0x18003020e  mov     dword ptr [rsi+50h], 1C08h
0x180030215  sbb     rcx, rcx
0x180030218  mov     dword ptr [rsi+54h], 8
0x18003021f  and     rcx, 0FFFFFFFFFFFFFFF7h
0x180030223  mov     dword ptr [rsi+84h], 2
0x18003022d  add     rcx, 113Ah
0x180030234  mov     qword ptr [rsi+58h], 2Dh ; '-'
0x18003023c  neg     edx
0x18003023e  mov     [rsi+68h], rcx
0x180030242  mov     rcx, rsi; this
0x180030245  mov     [rsi+0D0h], rsi
0x18003024c  sbb     rax, rax
0x18003024f  and     rax, 0FFFFFFFFFFFFFFF7h
0x180030253  add     rax, 113Bh
0x180030259  mov     [rsi+70h], rax
0x18003025d  lea     rax, asc_180055438; "    "
0x180030264  mov     [rsi+0C0h], rax
0x18003026b  lea     rax, ?_ProgressCallbackProc@CEncryptionProgressDialog@@CAJPEAUHWND__@@I_K_J2@Z; CEncryptionProgressDialog::_ProgressCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180030272  mov     [rsi+0C8h], rax
0x180030279  call    ?_InitErrorConfigInfo@CEncryptionProgressDialog@@AEAAXXZ; CEncryptionProgressDialog::_InitErrorConfigInfo(void)
0x18003027e  lea     ebx, [rdi+1]
0x180030281  xor     r9d, r9d; lpName
0x180030284  mov     edx, ebx; bManualReset
0x180030286  xor     r8d, r8d; bInitialState
0x180030289  xor     ecx, ecx; lpEventAttributes
0x18003028b  call    cs:__imp_CreateEventW
0x180030291  mov     [rsi+1B0h], rax
0x180030298  test    rax, rax
0x18003029b  jnz     short loc_1800302A8
0x18003029d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800302a2  mov     edi, eax
0x1800302a4  test    eax, eax
0x1800302a6  js      short loc_1800302EE
0x1800302a8  xor     r9d, r9d; lpName
0x1800302ab  xor     r8d, r8d; bInitialState
0x1800302ae  mov     edx, ebx; bManualReset
0x1800302b0  xor     ecx, ecx; lpEventAttributes
0x1800302b2  call    cs:__imp_CreateEventW
0x1800302b8  mov     [rsi+1A8h], rax
0x1800302bf  test    rax, rax
0x1800302c2  jnz     short loc_1800302CF
0x1800302c4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800302c9  mov     edi, eax
0x1800302cb  test    eax, eax
0x1800302cd  js      short loc_1800302EE
0x1800302cf  mov     edx, 0Ah; cItemGrow
0x1800302d4  lea     ecx, [rdx-6]; cbItem
0x1800302d7  call    DSA_Create
0x1800302dc  test    rax, rax
0x1800302df  mov     [rsi+1D0h], rax
0x1800302e6  mov     ecx, 8007000Eh
0x1800302eb  cmovz   edi, ecx
0x1800302ee  mov     rbx, [rsp+28h+arg_0]
0x1800302f3  mov     eax, edi
0x1800302f5  mov     rsi, [rsp+28h+arg_8]
0x1800302fa  add     rsp, 20h
0x1800302fe  pop     rdi
0x1800302ff  retn
```
