# CSystemWriter::Initialize(void)

- ea: `0x18001e494`
- end: `0x18001e511`
- name: `?Initialize@CSystemWriter@@AEAA_NXZ`
- size: `125`
- prototype: `bool __fastcall(CSystemWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e5e0`

## callees

- `0x180006e54`
- `0x18001e494`
- `0x18001e518`
- `0x180022010`

## string_xrefs

- `0x18001e4bf`: `System Writer object failed to initialize VSS.`
- `0x18001e4f3`: `System Writer object failed to subscribe to VSS.`

## pseudocode

```c
char __fastcall CSystemWriter::Initialize(CSystemWriter *this)
{
  struct CSystemWriter *v1; // rbx
  unsigned int v2; // eax
  const unsigned __int16 *v3; // rdx
  __int64 v4; // rcx
  char v5; // bl
  __int128 v7; // [rsp+50h] [rbp-18h] BYREF

  v1 = CSystemWriter::sm_pWriter;
  v7 = xmmword_180028738;
  v2 = CVssWriterEx::Initialize((__int64)CSystemWriter::sm_pWriter, &v7);
  if ( v2 )
  {
    v3 = L"System Writer object failed to initialize VSS.";
LABEL_7:
    CSystemWriter::LogSystemErrorEvent(0x200u, v3, v2);
    return 0;
  }
  v4 = *((_QWORD *)v1 + 1);
  if ( !v4 )
  {
    v2 = -2147467259;
LABEL_6:
    v3 = L"System Writer object failed to subscribe to VSS.";
    goto LABEL_7;
  }
  v5 = 1;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, 0xFFFFFFFFLL, 6);
  if ( v2 )
    goto LABEL_6;
  return v5;
}

```

## disassembly

```asm
0x18001e494  push    rbx
0x18001e496  sub     rsp, 60h
0x18001e49a  movups  xmm0, cs:xmmword_180028738
0x18001e4a1  mov     rbx, cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA; CSystemWriter * CSystemWriter::sm_pWriter
0x18001e4a8  lea     rdx, [rsp+68h+var_18]
0x18001e4ad  mov     rcx, rbx
0x18001e4b0  movdqu  [rsp+68h+var_18], xmm0
0x18001e4b6  call    ?Initialize@CVssWriterEx@@QEAAJU_GUID@@PEBGW4VSS_USAGE_TYPE@@W4VSS_SOURCE_TYPE@@W4_VSS_APPLICATION_LEVEL@@KW4VSS_ALTERNATE_WRITER_STATE@@_N1@Z; CVssWriterEx::Initialize(_GUID,ushort const *,VSS_USAGE_TYPE,VSS_SOURCE_TYPE,_VSS_APPLICATION_LEVEL,ulong,VSS_ALTERNATE_WRITER_STATE,bool,ushort const *)
0x18001e4bb  test    eax, eax
0x18001e4bd  jz      short loc_18001E4C8
0x18001e4bf  lea     rdx, aSystemWriterOb_0; "System Writer object failed to initiali"...
0x18001e4c6  jmp     short loc_18001E4FA
0x18001e4c8  mov     rcx, [rbx+8]
0x18001e4cc  test    rcx, rcx
0x18001e4cf  jnz     short loc_18001E4D8
0x18001e4d1  mov     eax, 80004005h
0x18001e4d6  jmp     short loc_18001E4F3
0x18001e4d8  mov     rax, [rcx]
0x18001e4db  mov     r8d, 6
0x18001e4e1  or      edx, 0FFFFFFFFh
0x18001e4e4  mov     bl, 1
0x18001e4e6  mov     rax, [rax+20h]
0x18001e4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ef  test    eax, eax
0x18001e4f1  jz      short loc_18001E509
0x18001e4f3  lea     rdx, aSystemWriterOb; "System Writer object failed to subscrib"...
0x18001e4fa  mov     r8d, eax; unsigned int
0x18001e4fd  mov     ecx, 200h; unsigned int
0x18001e502  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001e507  xor     bl, bl
0x18001e509  mov     al, bl
0x18001e50b  add     rsp, 60h
0x18001e50f  pop     rbx
0x18001e510  retn
```
