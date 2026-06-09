# COMPRESSION_CONTEXT::ProcessEncodedChunkHeader(void)

- ea: `0x1800068b0`
- end: `0x180006998`
- name: `?ProcessEncodedChunkHeader@COMPRESSION_CONTEXT@@QEAAJXZ`
- size: `232`
- prototype: `signed int __fastcall(COMPRESSION_CONTEXT *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002820`

## callees

- `0x180006588`
- `0x18000664c`
- `0x18000674c`
- `0x1800068b0`

## pseudocode

```c
signed int __fastcall COMPRESSION_CONTEXT::ProcessEncodedChunkHeader(COMPRESSION_CONTEXT *this)
{
  signed int result; // eax

  while ( (!*((_DWORD *)this + 5) || *((_DWORD *)this + 6) != 5) && *((_DWORD *)this + 24) < *((_DWORD *)this + 22) )
  {
    switch ( *((_DWORD *)this + 6) )
    {
      case 0:
        result = COMPRESSION_CONTEXT::CalculateEncodedChunkByteCount(this);
        if ( result >= 0 )
          continue;
        return result;
      case 1:
        result = COMPRESSION_CONTEXT::DeleteEncodedChunkExtension(this);
        if ( result >= 0 )
          continue;
        return result;
      case 2:
        result = COMPRESSION_CONTEXT::IncrementPointerInULChunk(this, 1u);
        if ( result < 0 )
          return result;
        *((_DWORD *)this + 6) = 5;
        break;
      case 3:
        result = COMPRESSION_CONTEXT::IncrementPointerInULChunk(this, 1u);
        if ( result < 0 )
          return result;
        *((_DWORD *)this + 6) = 4;
        break;
      case 4:
        result = COMPRESSION_CONTEXT::IncrementPointerInULChunk(this, 1u);
        if ( result < 0 )
          return result;
        *((_DWORD *)this + 6) = 0;
        break;
      case 5:
        *((_DWORD *)this + 6) = 3;
        continue;
      default:
        continue;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800068b0  mov     [rsp+arg_0], rbx
0x1800068b5  push    rdi
0x1800068b6  sub     rsp, 20h
0x1800068ba  mov     rbx, rcx
0x1800068bd  lea     rdi, cs:180000000h
0x1800068c4  cmp     dword ptr [rbx+14h], 0; jumptable 00000001800068F3 default case
0x1800068c8  jz      short loc_1800068D4
0x1800068ca  cmp     dword ptr [rbx+18h], 5
0x1800068ce  jz      loc_180006971
0x1800068d4  mov     eax, [rbx+58h]
0x1800068d7  cmp     [rbx+60h], eax
0x1800068da  jnb     loc_180006971
0x1800068e0  movsxd  rax, dword ptr [rbx+18h]
0x1800068e4  cmp     eax, 5; switch 6 cases
0x1800068e7  ja      short def_1800068F3; jumptable 00000001800068F3 default case
0x1800068e9  mov     ecx, ds:(jpt_1800068F3 - 180000000h)[rdi+rax*4]
0x1800068f0  add     rcx, rdi
0x1800068f3  jmp     rcx; switch jump
0x1800068f5  mov     rcx, rbx; jumptable 00000001800068F3 case 0
0x1800068f8  call    ?CalculateEncodedChunkByteCount@COMPRESSION_CONTEXT@@QEAAJXZ; COMPRESSION_CONTEXT::CalculateEncodedChunkByteCount(void)
0x1800068fd  test    eax, eax
0x1800068ff  jns     short def_1800068F3; jumptable 00000001800068F3 default case
0x180006901  jmp     short loc_180006973
0x180006903  mov     rcx, rbx; jumptable 00000001800068F3 case 1
0x180006906  call    ?DeleteEncodedChunkExtension@COMPRESSION_CONTEXT@@QEAAJXZ; COMPRESSION_CONTEXT::DeleteEncodedChunkExtension(void)
0x18000690b  test    eax, eax
0x18000690d  jns     short def_1800068F3; jumptable 00000001800068F3 default case
0x18000690f  jmp     short loc_180006973
0x180006911  mov     edx, 1; jumptable 00000001800068F3 case 2
0x180006916  mov     rcx, rbx; this
0x180006919  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x18000691e  test    eax, eax
0x180006920  js      short loc_180006973
0x180006922  mov     dword ptr [rbx+18h], 5
0x180006929  jmp     short def_1800068F3; jumptable 00000001800068F3 default case
0x18000692b  mov     edx, 1; jumptable 00000001800068F3 case 3
0x180006930  mov     rcx, rbx; this
0x180006933  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x180006938  test    eax, eax
0x18000693a  js      short loc_180006973
0x18000693c  mov     dword ptr [rbx+18h], 4
0x180006943  jmp     def_1800068F3; jumptable 00000001800068F3 default case
0x180006948  mov     edx, 1; jumptable 00000001800068F3 case 4
0x18000694d  mov     rcx, rbx; this
0x180006950  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x180006955  test    eax, eax
0x180006957  js      short loc_180006973
0x180006959  mov     dword ptr [rbx+18h], 0
0x180006960  jmp     def_1800068F3; jumptable 00000001800068F3 default case
0x180006965  mov     dword ptr [rbx+18h], 3; jumptable 00000001800068F3 case 5
0x18000696c  jmp     def_1800068F3; jumptable 00000001800068F3 default case
0x180006971  xor     eax, eax
0x180006973  mov     rbx, [rsp+28h+arg_0]
0x180006978  add     rsp, 20h
0x18000697c  pop     rdi
0x18000697d  retn
```
