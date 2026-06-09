# COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)

- ea: `0x18000674c`
- end: `0x1800067f1`
- name: `?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z`
- size: `165`
- prototype: `__int64 __fastcall(COMPRESSION_CONTEXT *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006588`
- `0x18000664c`
- `0x1800068b0`

## callees

- `0x180002d30`
- `0x18000674c`
- `0x1800069a0`

## pseudocode

```c
signed int __fastcall COMPRESSION_CONTEXT::IncrementPointerInULChunk(COMPRESSION_CONTEXT *this, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int BytesAvailable; // eax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // esi
  __int64 v8; // r8
  signed int result; // eax

  v2 = a2;
  if ( a2 )
  {
    while ( *((_DWORD *)this + 24) < *((_DWORD *)this + 22) )
    {
      BytesAvailable = COMPRESSION_CONTEXT::QueryBytesAvailable(this);
      v6 = *((_DWORD *)this + 28);
      v7 = BytesAvailable;
      if ( BytesAvailable > v2 )
      {
        if ( v6 )
        {
          *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) += v2;
          *(_DWORD *)(*((_QWORD *)this + 13) + 16LL) -= v2;
        }
        else
        {
          *((_DWORD *)this + 34) += v2;
        }
        return 0;
      }
      v8 = *((_QWORD *)this + 13);
      if ( v6 )
      {
        *((_DWORD *)this + 24) = v5 + 1;
        *((_QWORD *)this + 13) = v8 + 32;
      }
      else
      {
        *((_DWORD *)this + 34) += BytesAvailable;
        if ( !*(_QWORD *)(v8 + 16) )
        {
          *((_DWORD *)this + 24) = v5 + 1;
          *((_QWORD *)this + 13) = v8 + 32;
        }
      }
      result = COMPRESSION_CONTEXT::SetupCurrentULChunk(this);
      if ( result < 0 )
        return result;
      v2 -= v7;
      if ( !v2 )
        return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000674c  mov     [rsp+arg_0], rbx
0x180006751  mov     [rsp+arg_8], rsi
0x180006756  push    rdi
0x180006757  sub     rsp, 20h
0x18000675b  mov     edi, edx
0x18000675d  mov     rbx, rcx
0x180006760  test    edx, edx
0x180006762  jz      short loc_1800067DF
0x180006764  mov     edx, [rbx+60h]
0x180006767  cmp     edx, [rbx+58h]
0x18000676a  jnb     short loc_1800067DF
0x18000676c  mov     rcx, rbx; this
0x18000676f  call    ?QueryBytesAvailable@COMPRESSION_CONTEXT@@QEAAKXZ; COMPRESSION_CONTEXT::QueryBytesAvailable(void)
0x180006774  mov     ecx, [rbx+70h]
0x180006777  mov     esi, eax
0x180006779  cmp     eax, edi
0x18000677b  ja      short loc_1800067C2
0x18000677d  mov     r8, [rbx+68h]
0x180006781  test    ecx, ecx
0x180006783  jz      short loc_180006795
0x180006785  lea     ecx, [rdx+1]
0x180006788  mov     [rbx+60h], ecx
0x18000678b  lea     rcx, [r8+20h]
0x18000678f  mov     [rbx+68h], rcx
0x180006793  jmp     short loc_1800067B0
0x180006795  add     [rbx+88h], esi
0x18000679b  cmp     qword ptr [r8+10h], 0
0x1800067a0  jnz     short loc_1800067B0
0x1800067a2  lea     eax, [rdx+1]
0x1800067a5  mov     [rbx+60h], eax
0x1800067a8  lea     rax, [r8+20h]
0x1800067ac  mov     [rbx+68h], rax
0x1800067b0  mov     rcx, rbx; this
0x1800067b3  call    ?SetupCurrentULChunk@COMPRESSION_CONTEXT@@QEAAJXZ; COMPRESSION_CONTEXT::SetupCurrentULChunk(void)
0x1800067b8  test    eax, eax
0x1800067ba  js      short loc_1800067E1
0x1800067bc  sub     edi, esi
0x1800067be  jnz     short loc_180006764
0x1800067c0  jmp     short loc_1800067DF
0x1800067c2  test    ecx, ecx
0x1800067c4  jz      short loc_1800067D9
0x1800067c6  mov     rcx, [rbx+68h]
0x1800067ca  mov     eax, edi
0x1800067cc  add     [rcx+8], rax
0x1800067d0  mov     rax, [rbx+68h]
0x1800067d4  sub     [rax+10h], edi
0x1800067d7  jmp     short loc_1800067DF
0x1800067d9  add     [rbx+88h], edi
0x1800067df  xor     eax, eax
0x1800067e1  mov     rbx, [rsp+28h+arg_0]
0x1800067e6  mov     rsi, [rsp+28h+arg_8]
0x1800067eb  add     rsp, 20h
0x1800067ef  pop     rdi
0x1800067f0  retn
```
