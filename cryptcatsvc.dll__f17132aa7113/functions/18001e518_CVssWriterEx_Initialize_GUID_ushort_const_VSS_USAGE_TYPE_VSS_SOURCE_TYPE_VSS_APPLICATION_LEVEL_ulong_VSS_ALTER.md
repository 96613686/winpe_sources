# CVssWriterEx::Initialize(_GUID,ushort const *,VSS_USAGE_TYPE,VSS_SOURCE_TYPE,_VSS_APPLICATION_LEVEL,ulong,VSS_ALTERNATE_WRITER_STATE,bool,ushort const *)

- ea: `0x18001e518`
- end: `0x18001e5d5`
- name: `?Initialize@CVssWriterEx@@QEAAJU_GUID@@PEBGW4VSS_USAGE_TYPE@@W4VSS_SOURCE_TYPE@@W4_VSS_APPLICATION_LEVEL@@KW4VSS_ALTERNATE_WRITER_STATE@@_N1@Z`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e494`

## callees

- `0x18001e518`
- `0x180022010`

## import_xrefs

- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriterEx` at `0x18001e53f`
- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriterEx` at `0x18001e53f`

## string_xrefs

- `0x18001e54c`: `System Writer`

## pseudocode

```c
__int64 __fastcall CVssWriterEx::Initialize(__int64 a1, __int128 *a2)
{
  _QWORD *v2; // rbx
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char); // rax
  int v7; // edi
  char v8; // [rsp+58h] [rbp-30h]
  __int128 v9; // [rsp+70h] [rbp-18h] BYREF

  v2 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8) )
    return 2147500037LL;
  result = CreateWriterEx(a1, a1 + 8);
  if ( (int)result >= 0 )
  {
    v5 = *v2;
    v8 = 0;
    v6 = *(__int64 (__fastcall **)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char))(*(_QWORD *)*v2 + 24LL);
    v9 = *a2;
    v7 = v6(v5, &v9, L"System Writer", 0, 0, 0, 1, 3, 1, 60000, 1, v8);
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      *v2 = 0;
    }
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001e518  mov     [rsp+arg_0], rbx
0x18001e51d  push    rdi
0x18001e51e  sub     rsp, 80h
0x18001e525  lea     rbx, [rcx+8]
0x18001e529  mov     rdi, rdx
0x18001e52c  cmp     qword ptr [rbx], 0
0x18001e530  jz      short loc_18001E53C
0x18001e532  mov     eax, 80004005h
0x18001e537  jmp     loc_18001E5C4
0x18001e53c  mov     rdx, rbx
0x18001e53f  call    cs:__imp_CreateWriterEx
0x18001e545  test    eax, eax
0x18001e547  js      short loc_18001E5C4
0x18001e549  mov     rcx, [rbx]
0x18001e54c  lea     r8, aSystemWriter; "System Writer"
0x18001e553  movaps  xmm0, xmmword ptr [rdi]
0x18001e556  mov     edx, 1
0x18001e55b  mov     [rsp+88h+var_30], 0
0x18001e560  xor     r9d, r9d
0x18001e563  mov     [rsp+88h+var_38], edx
0x18001e567  mov     rax, [rcx]
0x18001e56a  mov     [rsp+88h+var_40], 0EA60h
0x18001e572  mov     [rsp+88h+var_48], edx
0x18001e576  mov     [rsp+88h+var_50], 3
0x18001e57e  mov     rax, [rax+18h]
0x18001e582  mov     [rsp+88h+var_58], edx
0x18001e586  lea     rdx, [rsp+88h+var_18]
0x18001e58b  mov     [rsp+88h+var_60], 0
0x18001e593  movdqa  [rsp+88h+var_18], xmm0
0x18001e599  mov     [rsp+88h+var_68], 0
0x18001e5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5a6  mov     edi, eax
0x18001e5a8  test    eax, eax
0x18001e5aa  jns     short loc_18001E5C2
0x18001e5ac  mov     rcx, [rbx]
0x18001e5af  mov     rdx, [rcx]
0x18001e5b2  mov     rax, [rdx+10h]
0x18001e5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5bb  mov     qword ptr [rbx], 0
0x18001e5c2  mov     eax, edi
0x18001e5c4  mov     rbx, [rsp+88h+arg_0]
0x18001e5cc  add     rsp, 80h
0x18001e5d3  pop     rdi
0x18001e5d4  retn
```
