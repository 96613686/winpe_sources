# CNtfsSTATSTGArray::Init(void *)

- ea: `0x1800539a0`
- end: `0x180053a5d`
- name: `?Init@CNtfsSTATSTGArray@@QEAAJPEAX@Z`
- size: `189`
- prototype: `int(CNtfsSTATSTGArray *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053910`

## callees

- `0x180033dd0`
- `0x1800539a0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800539d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800539d4`

## pseudocode

```c
__int64 __fastcall CNtfsSTATSTGArray::Init(CNtfsSTATSTGArray *this, void *a2)
{
  _QWORD *v2; // rdi
  int v5; // r9d
  void *v6; // rcx
  int v7; // esi
  int v8; // edx
  struct _FILE_STREAM_INFORMATION *v9; // rcx
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  struct _FILE_STREAM_INFORMATION *v12; // [rsp+40h] [rbp+18h] BYREF

  v2 = (_QWORD *)((char *)this + 8);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1), 0xFFFFFFFFLL);
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 6) = 0;
  }
  v12 = 0;
  v11 = 0;
  v7 = EnumNtStreams(a2, &v12, &v11, v5);
  if ( v7 >= 0 )
  {
    v8 = 0;
    v9 = v12;
    if ( v12 )
    {
      do
      {
        ++v8;
        if ( !v9->NextEntryOffset )
          break;
        v9 = (struct _FILE_STREAM_INFORMATION *)((char *)v9 + v9->NextEntryOffset);
      }
      while ( v9 );
      v2 = (_QWORD *)((char *)this + 8);
    }
    *((_QWORD *)this + 2) = v12;
    v7 = 0;
    *((_DWORD *)this + 6) = v8;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 32LL))(*v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800539a0  mov     [rsp+arg_8], rbx
0x1800539a5  mov     [rsp+arg_18], rsi
0x1800539aa  push    rdi
0x1800539ab  sub     rsp, 20h
0x1800539af  lea     rdi, [rcx+8]
0x1800539b3  mov     rbx, rcx
0x1800539b6  mov     rcx, [rdi]
0x1800539b9  mov     rsi, rdx
0x1800539bc  or      edx, 0FFFFFFFFh
0x1800539bf  mov     rax, [rcx]
0x1800539c2  mov     rax, [rax+18h]
0x1800539c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539cb  mov     rcx, [rbx+10h]; pv
0x1800539cf  test    rcx, rcx
0x1800539d2  jz      short loc_1800539E9
0x1800539d4  call    cs:__imp_CoTaskMemFree
0x1800539da  mov     qword ptr [rbx+10h], 0
0x1800539e2  mov     dword ptr [rbx+18h], 0
0x1800539e9  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x1800539ee  mov     [rsp+28h+arg_10], 0
0x1800539f7  lea     rdx, [rsp+28h+arg_10]; struct _FILE_STREAM_INFORMATION **
0x1800539fc  mov     [rsp+28h+arg_0], 0
0x180053a04  mov     rcx, rsi; FileHandle
0x180053a07  call    ?EnumNtStreams@@YAJPEAXPEAPEAU_FILE_STREAM_INFORMATION@@PEAKH@Z; EnumNtStreams(void *,_FILE_STREAM_INFORMATION * *,ulong *,int)
0x180053a0c  mov     esi, eax
0x180053a0e  test    eax, eax
0x180053a10  js      short loc_180053A3C
0x180053a12  mov     r8, [rsp+28h+arg_10]
0x180053a17  xor     edx, edx
0x180053a19  mov     rcx, r8
0x180053a1c  test    r8, r8
0x180053a1f  jz      short loc_180053A33
0x180053a21  inc     edx
0x180053a23  cmp     dword ptr [rcx], 0
0x180053a26  jz      short loc_180053A2F
0x180053a28  mov     eax, [rcx]
0x180053a2a  add     rcx, rax
0x180053a2d  jnz     short loc_180053A21
0x180053a2f  lea     rdi, [rbx+8]
0x180053a33  mov     [rbx+10h], r8
0x180053a37  xor     esi, esi
0x180053a39  mov     [rbx+18h], edx
0x180053a3c  mov     rcx, [rdi]
0x180053a3f  mov     rdx, [rcx]
0x180053a42  mov     rax, [rdx+20h]
0x180053a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a4b  mov     rbx, [rsp+28h+arg_8]
0x180053a50  mov     eax, esi
0x180053a52  mov     rsi, [rsp+28h+arg_18]
0x180053a57  add     rsp, 20h
0x180053a5b  pop     rdi
0x180053a5c  retn
```
