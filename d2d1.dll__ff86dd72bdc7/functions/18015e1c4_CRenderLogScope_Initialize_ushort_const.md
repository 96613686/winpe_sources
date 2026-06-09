# CRenderLogScope::Initialize(ushort const *)

- ea: `0x18015e1c4`
- end: `0x18015e2f2`
- name: `?Initialize@CRenderLogScope@@QEAAJPEBG@Z`
- size: `302`
- prototype: `__int64 __fastcall(LPSTREAM *this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180096440`
- `0x18009674c`
- `0x18015c58c`
- `0x1802056d0`
- `0x180205820`
- `0x180207290`
- `0x180232030`

## callees

- `0x18001fd58`
- `0x18015e1c4`
- `0x1802cc680`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18015e229`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18015e229`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18015e2b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18015e2b2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18015e216`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18015e216`

## pseudocode

```c
__int64 __fastcall CRenderLogScope::Initialize(LPSTREAM *this, const unsigned __int16 *a2)
{
  HRESULT StreamOnHGlobal; // ebx
  struct IXmlWriter *v5; // rdx
  LPSTREAM v7; // rcx
  LPSTREAM v8; // rdx
  ULONGLONG TickCount64; // rsi

  StreamOnHGlobal = 0;
  if ( *((_BYTE *)*this + 4840) )
  {
    TickCount64 = GetTickCount64();
    if ( !*((_QWORD *)*this + 588) && (!*((_BYTE *)*this + 4841) || TickCount64 - qword_1805DBF08 > 0x3E8) )
    {
      StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, this + 5);
      if ( StreamOnHGlobal < 0
        || (OutputDebugStringA("\n\nD2D Imaging Render Log:\n"),
            v7 = *this,
            v8 = this[5],
            qword_1805DBF08 = TickCount64,
            StreamOnHGlobal = (*(__int64 (__fastcall **)(LPSTREAM, LPSTREAM, _QWORD))(*(_QWORD *)v7 + 32LL))(
                                v7,
                                v8,
                                *((unsigned int *)v7 + 1211)),
            StreamOnHGlobal < 0) )
      {
LABEL_4:
        DoStackCapture(StreamOnHGlobal);
        return (unsigned int)StreamOnHGlobal;
      }
    }
  }
  v5 = (struct IXmlWriter *)*((_QWORD *)*this + 588);
  if ( v5 )
  {
    StreamOnHGlobal = CRenderGraphLogger::BeginLog(
                        (CRenderGraphLogger *)(this + 2),
                        v5,
                        a2,
                        (*((_DWORD *)*this + 1178) & 8) != 0,
                        (*((_DWORD *)*this + 1178) & 0x20) != 0,
                        (*((_DWORD *)*this + 1178) & 0x10) != 0,
                        (*((_DWORD *)*this + 1178) & 0x40) != 0);
    if ( StreamOnHGlobal >= 0 )
    {
      *((_BYTE *)this + 8) = 1;
      return (unsigned int)StreamOnHGlobal;
    }
    goto LABEL_4;
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18015e1c4  push    rbx
0x18015e1c6  push    rbp
0x18015e1c7  push    rsi
0x18015e1c8  push    rdi
0x18015e1c9  push    r14
0x18015e1cb  sub     rsp, 40h
0x18015e1cf  mov     rax, [rcx]
0x18015e1d2  xor     ebx, ebx
0x18015e1d4  mov     rbp, rdx
0x18015e1d7  mov     rdi, rcx
0x18015e1da  cmp     [rax+12E8h], bl
0x18015e1e0  jnz     loc_18015E2B2
0x18015e1e6  mov     r9, [rdi]
0x18015e1e9  mov     rdx, [r9+1260h]; struct IXmlWriter *
0x18015e1f0  test    rdx, rdx
0x18015e1f3  jnz     short loc_18015E258
0x18015e1f5  mov     eax, ebx
0x18015e1f7  add     rsp, 40h
0x18015e1fb  pop     r14
0x18015e1fd  pop     rdi
0x18015e1fe  pop     rsi
0x18015e1ff  pop     rbp
0x18015e200  pop     rbx
0x18015e201  retn
0x18015e202  mov     ecx, ebx; int
0x18015e204  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18015e209  jmp     short loc_18015E1F5
0x18015e20b  lea     r8, [rdi+28h]; ppstm
0x18015e20f  mov     edx, 1; fDeleteOnRelease
0x18015e214  xor     ecx, ecx; hGlobal
0x18015e216  call    cs:__imp_CreateStreamOnHGlobal
0x18015e21c  mov     ebx, eax
0x18015e21e  test    eax, eax
0x18015e220  js      short loc_18015E202
0x18015e222  lea     rcx, OutputString; "\n\nD2D Imaging Render Log:\n"
0x18015e229  call    cs:__imp_OutputDebugStringA
0x18015e22f  mov     rcx, [rdi]
0x18015e232  mov     rdx, [rdi+28h]
0x18015e236  mov     cs:qword_1805DBF08, rsi
0x18015e23d  mov     rax, [rcx]
0x18015e240  mov     r8d, [rcx+12ECh]
0x18015e247  mov     rax, [rax+20h]
0x18015e24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015e250  mov     ebx, eax
0x18015e252  test    eax, eax
0x18015e254  js      short loc_18015E202
0x18015e256  jmp     short loc_18015E1E6
0x18015e258  mov     r9d, [r9+1268h]
0x18015e25f  lea     rcx, [rdi+10h]; this
0x18015e263  mov     r8d, r9d
0x18015e266  mov     r10d, r9d
0x18015e269  mov     eax, r9d
0x18015e26c  shr     r8d, 4
0x18015e270  and     r8b, 1
0x18015e274  shr     r10d, 6
0x18015e278  and     r10b, 1
0x18015e27c  shr     eax, 5
0x18015e27f  mov     [rsp+68h+var_38], r10b; bool
0x18015e284  and     al, 1
0x18015e286  mov     [rsp+68h+var_40], r8b; bool
0x18015e28b  mov     r8, rbp; unsigned __int16 *
0x18015e28e  shr     r9d, 3
0x18015e292  and     r9b, 1; bool
0x18015e296  mov     [rsp+68h+var_48], al; bool
0x18015e29a  call    ?BeginLog@CRenderGraphLogger@@QEAAJPEAUIXmlWriter@@PEBG_N222@Z; CRenderGraphLogger::BeginLog(IXmlWriter *,ushort const *,bool,bool,bool,bool)
0x18015e29f  mov     ebx, eax
0x18015e2a1  test    eax, eax
0x18015e2a3  js      loc_18015E202
0x18015e2a9  mov     byte ptr [rdi+8], 1
0x18015e2ad  jmp     loc_18015E1F5
0x18015e2b2  call    cs:__imp_GetTickCount64
0x18015e2b8  mov     rsi, rax
0x18015e2bb  mov     rax, [rdi]
0x18015e2be  cmp     [rax+1260h], rbx
0x18015e2c5  jnz     loc_18015E1E6
0x18015e2cb  cmp     [rax+12E9h], bl
0x18015e2d1  jz      loc_18015E20B
0x18015e2d7  mov     rax, rsi
0x18015e2da  sub     rax, cs:qword_1805DBF08
0x18015e2e1  cmp     rax, 3E8h
0x18015e2e7  jbe     loc_18015E1E6
0x18015e2ed  jmp     loc_18015E20B
```
