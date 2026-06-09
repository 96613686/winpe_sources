# CCscEvtGeneratorBase::EventWrite(void)

- ea: `0x18004c36c`
- end: `0x18004c41b`
- name: `?EventWrite@CCscEvtGeneratorBase@@QEAAKXZ`
- size: `175`
- prototype: `unsigned int __fastcall(CCscEvtGeneratorBase *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004bf68`
- `0x18004c0fc`
- `0x18004c198`
- `0x18004c234`

## callees

- `0x18004c36c`
- `0x18004c4b0`
- `0x18004d010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004c401`
- `ntdll!EtwEventWrite` at `0x18004c401`
- `ntdll!EtwEventEnabled` at `0x18004c3c1`
- `ntdll!EtwEventEnabled` at `0x18004c3c1`

## pseudocode

```c
__int64 __fastcall CCscEvtGeneratorBase::EventWrite(CCscEvtGeneratorBase *this)
{
  unsigned int Publisher; // edi
  int v3; // esi
  __int64 v4; // rax
  unsigned __int64 v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  Publisher = CCscEvtGeneratorBase::_GetPublisher(this, &v7);
  if ( !Publisher )
  {
    v3 = *((_DWORD *)this + 8);
    if ( !*((_DWORD *)this + 9) )
    {
      v6 = 0;
      if ( !CCscEvtGeneratorBase::_GetPublisher(this, &v6) )
      {
        v3 = (unsigned __int8)EtwEventEnabled(v6, *((_QWORD *)this + 3));
        *((_DWORD *)this + 8) = v3;
        *((_DWORD *)this + 9) = 1;
      }
    }
    if ( v3 )
    {
      if ( *((_DWORD *)this + 10) )
        v4 = (***((__int64 (__fastcall ****)(_QWORD))this + 6))(*((_QWORD *)this + 6));
      else
        v4 = 0;
      return (unsigned int)EtwEventWrite(v7, *((_QWORD *)this + 3), *((unsigned int *)this + 10), v4);
    }
  }
  return Publisher;
}

```

## disassembly

```asm
0x18004c36c  mov     rax, rsp
0x18004c36f  mov     [rax+8], rbx
0x18004c373  mov     [rax+20h], rsi
0x18004c377  push    rdi
0x18004c378  sub     rsp, 20h
0x18004c37c  lea     rdx, [rax+18h]; unsigned __int64 *
0x18004c380  mov     qword ptr [rax+18h], 0
0x18004c388  mov     rbx, rcx
0x18004c38b  call    ?_GetPublisher@CCscEvtGeneratorBase@@AEAAKPEA_K@Z; CCscEvtGeneratorBase::_GetPublisher(unsigned __int64 *)
0x18004c390  mov     edi, eax
0x18004c392  test    eax, eax
0x18004c394  jnz     short loc_18004C409
0x18004c396  mov     esi, [rbx+20h]
0x18004c399  cmp     [rbx+24h], eax
0x18004c39c  jnz     short loc_18004C3D4
0x18004c39e  lea     rdx, [rsp+28h+arg_8]; unsigned __int64 *
0x18004c3a3  mov     [rsp+28h+arg_8], 0
0x18004c3ac  mov     rcx, rbx; this
0x18004c3af  call    ?_GetPublisher@CCscEvtGeneratorBase@@AEAAKPEA_K@Z; CCscEvtGeneratorBase::_GetPublisher(unsigned __int64 *)
0x18004c3b4  test    eax, eax
0x18004c3b6  jnz     short loc_18004C3D4
0x18004c3b8  mov     rdx, [rbx+18h]
0x18004c3bc  mov     rcx, [rsp+28h+arg_8]
0x18004c3c1  call    cs:__imp_EtwEventEnabled
0x18004c3c7  movzx   esi, al
0x18004c3ca  mov     [rbx+20h], esi
0x18004c3cd  mov     dword ptr [rbx+24h], 1
0x18004c3d4  test    esi, esi
0x18004c3d6  jz      short loc_18004C409
0x18004c3d8  cmp     dword ptr [rbx+28h], 0
0x18004c3dc  jz      short loc_18004C3EF
0x18004c3de  mov     rcx, [rbx+30h]
0x18004c3e2  mov     rax, [rcx]
0x18004c3e5  mov     rax, [rax]
0x18004c3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3ed  jmp     short loc_18004C3F1
0x18004c3ef  xor     eax, eax
0x18004c3f1  mov     r8d, [rbx+28h]
0x18004c3f5  mov     r9, rax
0x18004c3f8  mov     rdx, [rbx+18h]
0x18004c3fc  mov     rcx, [rsp+28h+arg_10]
0x18004c401  call    cs:__imp_EtwEventWrite
0x18004c407  mov     edi, eax
0x18004c409  mov     rbx, [rsp+28h+arg_0]
0x18004c40e  mov     eax, edi
0x18004c410  mov     rsi, [rsp+28h+arg_18]
0x18004c415  add     rsp, 20h
0x18004c419  pop     rdi
0x18004c41a  retn
```
