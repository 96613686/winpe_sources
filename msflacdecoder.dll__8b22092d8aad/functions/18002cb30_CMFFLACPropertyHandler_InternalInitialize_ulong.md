# CMFFLACPropertyHandler::InternalInitialize(ulong)

- ea: `0x18002cb30`
- end: `0x18002cc6d`
- name: `?InternalInitialize@CMFFLACPropertyHandler@@MEAAJK@Z`
- size: `317`
- prototype: `__int64 __fastcall(CMFFLACPropertyHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180020484`
- `0x18002cb30`
- `0x18002cca0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cba2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cba2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cb80`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cb80`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cbf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cbf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb67`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMFFLACPropertyHandler::InternalInitialize(CMFFLACPropertyHandler *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  void *v5; // rcx
  HANDLE EventW; // rax
  int v8; // eax
  __int64 v9; // rdx
  int SourceAsync; // [rsp+58h] [rbp+10h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1888);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1888));
  *((_DWORD *)this + 488) = a2;
  v5 = (void *)*((_QWORD *)this + 245);
  if ( v5 )
  {
    ResetEvent(v5);
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 245) = EventW;
    if ( !EventW )
    {
      v8 = -2147467259;
      SourceAsync = -2147467259;
      if ( !g_wppLevels )
        goto LABEL_7;
      v9 = 13;
      goto LABEL_11;
    }
  }
  SourceAsync = CMFFLACPropertyHandler::LoadSourceAsync(this);
  if ( SourceAsync >= 0 )
  {
    if ( WaitForSingleObject(*((HANDLE *)this + 245), 0x1388u) )
    {
      SourceAsync = -1072875795;
      goto LABEL_6;
    }
    v8 = *((_DWORD *)this + 492);
    SourceAsync = v8;
    if ( v8 >= 0 )
      goto LABEL_6;
    if ( !g_wppLevels )
      goto LABEL_7;
    v9 = 14;
LABEL_11:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids, this, v8);
    goto LABEL_7;
  }
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 242) + 80LL) + 96LL))(*((_QWORD *)this + 242) + 80LL);
LABEL_7:
  LeaveCriticalSection(v4);
  return (unsigned int)SourceAsync;
}

```

## disassembly

```asm
0x18002cb30  mov     r11, rsp
0x18002cb33  mov     [r11+18h], rbx
0x18002cb37  mov     [r11+20h], rsi
0x18002cb3b  push    rdi
0x18002cb3c  sub     rsp, 40h
0x18002cb40  mov     ebx, edx
0x18002cb42  mov     rdi, rcx
0x18002cb45  mov     [rsp+48h+arg_8], 0
0x18002cb4d  mov     [r11-18h], rcx
0x18002cb51  lea     rax, [r11+10h]
0x18002cb55  mov     [r11-10h], rax
0x18002cb59  lea     rsi, [rcx+760h]
0x18002cb60  mov     [r11+8], rsi
0x18002cb64  mov     rcx, rsi; lpCriticalSection
0x18002cb67  call    cs:__imp_EnterCriticalSection
0x18002cb6d  nop
0x18002cb6e  mov     [rdi+7A0h], ebx
0x18002cb74  mov     rcx, [rdi+7A8h]; hEvent
0x18002cb7b  test    rcx, rcx
0x18002cb7e  jz      short loc_18002CBEF
0x18002cb80  call    cs:__imp_ResetEvent
0x18002cb86  mov     rcx, rdi; this
0x18002cb89  call    ?LoadSourceAsync@CMFFLACPropertyHandler@@AEAAJXZ; CMFFLACPropertyHandler::LoadSourceAsync(void)
0x18002cb8e  mov     [rsp+48h+arg_8], eax
0x18002cb92  test    eax, eax
0x18002cb94  js      short loc_18002CBB8
0x18002cb96  mov     edx, 1388h; dwMilliseconds
0x18002cb9b  mov     rcx, [rdi+7A8h]; hHandle
0x18002cba2  call    cs:__imp_WaitForSingleObject
0x18002cba8  test    eax, eax
0x18002cbaa  jz      loc_18002CC46
0x18002cbb0  mov     [rsp+48h+arg_8], 0C00D36EDh
0x18002cbb8  mov     rcx, [rdi+790h]
0x18002cbbf  add     rcx, 50h ; 'P'
0x18002cbc3  mov     rax, [rcx]
0x18002cbc6  mov     rax, [rax+60h]
0x18002cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbcf  mov     ebx, [rsp+48h+arg_8]
0x18002cbd3  mov     rcx, rsi; lpCriticalSection
0x18002cbd6  call    cs:__imp_LeaveCriticalSection
0x18002cbdc  nop
0x18002cbdd  mov     eax, ebx
0x18002cbdf  mov     rbx, [rsp+48h+arg_10]
0x18002cbe4  mov     rsi, [rsp+48h+arg_18]
0x18002cbe9  add     rsp, 40h
0x18002cbed  pop     rdi
0x18002cbee  retn
0x18002cbef  xor     r9d, r9d; lpName
0x18002cbf2  xor     r8d, r8d; bInitialState
0x18002cbf5  xor     edx, edx; bManualReset
0x18002cbf7  xor     ecx, ecx; lpEventAttributes
0x18002cbf9  call    cs:__imp_CreateEventW
0x18002cbff  mov     [rdi+7A8h], rax
0x18002cc06  test    rax, rax
0x18002cc09  jnz     loc_18002CB86
0x18002cc0f  mov     eax, 80004005h
0x18002cc14  mov     [rsp+48h+arg_8], eax
0x18002cc18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002cc1f  jb      short loc_18002CBCF
0x18002cc21  mov     edx, 0Dh
0x18002cc26  mov     [rsp+48h+var_28], eax
0x18002cc2a  mov     r9, rdi
0x18002cc2d  lea     r8, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids
0x18002cc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc3b  mov     rcx, [rcx+10h]
0x18002cc3f  call    WPP_SF_qd
0x18002cc44  jmp     short loc_18002CBCF
0x18002cc46  mov     eax, [rdi+7B0h]
0x18002cc4c  mov     [rsp+48h+arg_8], eax
0x18002cc50  test    eax, eax
0x18002cc52  jns     loc_18002CBB8
0x18002cc58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002cc5f  jb      loc_18002CBCF
0x18002cc65  mov     edx, 0Eh
0x18002cc6a  jmp     short loc_18002CC26
```
