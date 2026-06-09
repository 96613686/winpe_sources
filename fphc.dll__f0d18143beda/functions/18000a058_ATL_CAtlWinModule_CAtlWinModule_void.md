# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000a058`
- end: `0x18000a10f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011cf0`

## callees

- `0x180005950`
- `0x18000a058`

## import_xrefs

- `msvcrt!free` at `0x18000a0af`
- `msvcrt!free` at `0x18000a0de`
- `msvcrt!free` at `0x18000a0af`
- `msvcrt!free` at `0x18000a0de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a0c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a0c9`
- `USER32!UnregisterClassA` at `0x18000a099`
- `USER32!UnregisterClassA` at `0x18000a099`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rsi
  int i; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x18000A10ELL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * i), v3);
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x18000a058  mov     [rsp+arg_0], rbx
0x18000a05d  mov     [rsp+arg_8], rsi
0x18000a062  push    rdi
0x18000a063  sub     rsp, 20h
0x18000a067  mov     rbx, rcx
0x18000a06a  test    rcx, rcx
0x18000a06d  jz      short loc_18000A0D5
0x18000a06f  cmp     dword ptr [rcx], 48h ; 'H'
0x18000a072  jnz     short loc_18000A0D5
0x18000a074  mov     rsi, cs:hInstance
0x18000a07b  xor     edi, edi
0x18000a07d  cmp     [rcx+40h], edi
0x18000a080  jle     short loc_18000A0A6
0x18000a082  test    edi, edi
0x18000a084  js      short loc_18000A104
0x18000a086  cmp     edi, [rbx+40h]
0x18000a089  jge     short loc_18000A104
0x18000a08b  mov     rax, [rbx+38h]
0x18000a08f  mov     rdx, rsi; hInstance
0x18000a092  movsxd  rcx, edi
0x18000a095  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000a099  call    cs:__imp_UnregisterClassA
0x18000a09f  inc     edi
0x18000a0a1  cmp     edi, [rbx+40h]
0x18000a0a4  jl      short loc_18000A082
0x18000a0a6  mov     rcx, [rbx+38h]; Block
0x18000a0aa  test    rcx, rcx
0x18000a0ad  jz      short loc_18000A0BD
0x18000a0af  call    cs:__imp_free
0x18000a0b5  mov     qword ptr [rbx+38h], 0
0x18000a0bd  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a0c1  mov     qword ptr [rbx+40h], 0
0x18000a0c9  call    cs:__imp_DeleteCriticalSection
0x18000a0cf  mov     dword ptr [rbx], 0
0x18000a0d5  mov     rcx, [rbx+38h]; Block
0x18000a0d9  test    rcx, rcx
0x18000a0dc  jz      short loc_18000A0EC
0x18000a0de  call    cs:__imp_free
0x18000a0e4  mov     qword ptr [rbx+38h], 0
0x18000a0ec  mov     rsi, [rsp+28h+arg_8]
0x18000a0f1  mov     qword ptr [rbx+40h], 0
0x18000a0f9  mov     rbx, [rsp+28h+arg_0]
0x18000a0fe  add     rsp, 20h
0x18000a102  pop     rdi
0x18000a103  retn
0x18000a104  mov     ecx, 0C000008Ch; unsigned int
0x18000a109  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
