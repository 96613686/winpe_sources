# DeviceTimeoutManager::Init(CD3DDeviceCommon *)

- ea: `0x18019a5b8`
- end: `0x18019a661`
- name: `?Init@DeviceTimeoutManager@@AEAAJPEAVCD3DDeviceCommon@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(DeviceTimeoutManager *__hidden this, struct CD3DDeviceCommon *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18019a4e8`

## callees

- `0x18001fd58`
- `0x18019a5b8`
- `0x18019a668`
- `0x18019a68c`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18019a60c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18019a60c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019a63d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019a63d`

## pseudocode

```c
__int64 __fastcall DeviceTimeoutManager::Init(DeviceTimeoutManager *this, enum D2D1_RENDERING_PRIORITY *a2)
{
  __int64 v3; // r8
  signed int v4; // ebx
  __int64 i; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax

  *(_QWORD *)this = a2;
  DeviceTimeoutManager::SetPixelFillLimitFromPriority(this, a2[38]);
  v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))(v3 + 104))(
         *(_QWORD *)(v3 + 104),
         &GUID_05008617_fbfd_4051_a790_144884b4f6a9,
         (char *)this + 8);
  if ( v4 < 0 )
  {
LABEL_10:
    DoStackCapture(v4);
    return (unsigned int)v4;
  }
  else
  {
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + i + 7) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_10;
      }
    }
    *((_BYTE *)this + 75) = CD3DDeviceCommon::ShouldCountPixels(*(CD3DDeviceCommon **)this);
    return 0;
  }
}

```

## disassembly

```asm
0x18019a5b8  mov     [rsp+arg_0], rbx
0x18019a5bd  mov     [rsp+arg_8], rsi
0x18019a5c2  push    rdi
0x18019a5c3  sub     rsp, 20h
0x18019a5c7  mov     [rcx], rdx
0x18019a5ca  mov     r8, rdx
0x18019a5cd  mov     edx, [rdx+98h]; enum D2D1_RENDERING_PRIORITY
0x18019a5d3  mov     rsi, rcx
0x18019a5d6  call    ?SetPixelFillLimitFromPriority@DeviceTimeoutManager@@QEAAXW4D2D1_RENDERING_PRIORITY@@@Z; DeviceTimeoutManager::SetPixelFillLimitFromPriority(D2D1_RENDERING_PRIORITY)
0x18019a5db  mov     rcx, [r8+68h]
0x18019a5df  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x18019a5e6  lea     r8, [rsi+8]
0x18019a5ea  mov     rax, [rcx]
0x18019a5ed  mov     rax, [rax]
0x18019a5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a5f5  mov     ebx, eax
0x18019a5f7  test    eax, eax
0x18019a5f9  js      short loc_18019A656
0x18019a5fb  xor     edi, edi
0x18019a5fd  cmp     edi, 2
0x18019a600  jnb     short loc_18019A620
0x18019a602  xor     r9d, r9d; lpName
0x18019a605  xor     r8d, r8d; bInitialState
0x18019a608  xor     edx, edx; bManualReset
0x18019a60a  xor     ecx, ecx; lpEventAttributes
0x18019a60c  call    cs:__imp_CreateEventW
0x18019a612  mov     [rsi+rdi*8+38h], rax
0x18019a617  test    rax, rax
0x18019a61a  jz      short loc_18019A63D
0x18019a61c  inc     edi
0x18019a61e  jmp     short loc_18019A5FD
0x18019a620  mov     rcx, [rsi]; this
0x18019a623  call    ?ShouldCountPixels@CD3DDeviceCommon@@QEBA_NXZ; CD3DDeviceCommon::ShouldCountPixels(void)
0x18019a628  mov     [rsi+4Bh], al
0x18019a62b  xor     eax, eax
0x18019a62d  mov     rbx, [rsp+28h+arg_0]
0x18019a632  mov     rsi, [rsp+28h+arg_8]
0x18019a637  add     rsp, 20h
0x18019a63b  pop     rdi
0x18019a63c  retn
0x18019a63d  call    cs:__imp_GetLastError
0x18019a643  mov     ebx, eax
0x18019a645  test    eax, eax
0x18019a647  jle     short loc_18019A652
0x18019a649  movzx   ebx, ax
0x18019a64c  or      ebx, 80070000h
0x18019a652  test    ebx, ebx
0x18019a654  jns     short loc_18019A61C
0x18019a656  mov     ecx, ebx; int
0x18019a658  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18019a65d  mov     eax, ebx
0x18019a65f  jmp     short loc_18019A62D
```
