# MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)

- ea: `0x180003900`
- end: `0x180003a43`
- name: `?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(MIME_MAP_TABLE *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180003de0`

## callees

- `0x180003900`
- `0x180003a50`
- `0x180009010`

## string_xrefs

- `0x1800039a3`: `fileExtension`

## pseudocode

```c
__int64 __fastcall MIME_MAP_TABLE::Initialize(MIME_MAP_TABLE *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct INativeConfigurationElement *, __int64 *); // rax
  int v5; // ebx
  unsigned int v6; // edi
  unsigned __int16 *v8; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v9; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v10; // [rsp+78h] [rbp+38h] BYREF
  __int64 v11; // [rsp+80h] [rbp+40h] BYREF
  __int64 v12; // [rsp+88h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a2;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v4 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(v2 + 40);
  v8 = 0;
  v9 = 0;
  v5 = v4(a2, &v12);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 24LL))(v12, &v10);
    if ( v5 >= 0 )
    {
      v6 = 0;
      if ( !v10 )
      {
LABEL_9:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return 0;
      }
      while ( 1 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 32LL))(v12, v6, &v11);
        if ( v5 < 0 )
          break;
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
               v11,
               L"fileExtension",
               &v8,
               0,
               0);
        if ( v5 < 0 )
          break;
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
               v11,
               L"mimeType",
               &v9,
               0,
               0);
        if ( v5 < 0 )
          break;
        v5 = MIME_MAP_TABLE::CreateAndAddMimeMapEntry(this, v9, v8);
        if ( v5 < 0 )
          break;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        ++v6;
        v11 = 0;
        if ( v6 >= v10 )
          goto LABEL_9;
      }
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003900  push    rbp
0x180003902  push    rbx
0x180003903  push    rsi
0x180003904  push    rdi
0x180003905  push    r14
0x180003907  mov     rbp, rsp
0x18000390a  sub     rsp, 40h
0x18000390e  mov     rax, [rdx]
0x180003911  xor     r14d, r14d
0x180003914  mov     r8, rdx
0x180003917  mov     [rbp+arg_18], r14
0x18000391b  mov     rsi, rcx
0x18000391e  mov     [rbp+arg_10], r14
0x180003922  lea     rdx, [rbp+arg_18]
0x180003926  mov     [rbp+arg_8], r14d
0x18000392a  mov     rax, [rax+28h]
0x18000392e  mov     rcx, r8
0x180003931  mov     [rbp+var_10], r14
0x180003935  mov     [rbp+var_8], r14
0x180003939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000393e  mov     ebx, eax
0x180003940  test    eax, eax
0x180003942  js      loc_1800071DC
0x180003948  mov     rcx, [rbp+arg_18]
0x18000394c  lea     rdx, [rbp+arg_8]
0x180003950  mov     rax, [rcx]
0x180003953  mov     rax, [rax+18h]
0x180003957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000395c  mov     ebx, eax
0x18000395e  test    eax, eax
0x180003960  js      loc_1800071DC
0x180003966  mov     edi, r14d
0x180003969  cmp     [rbp+arg_8], r14d
0x18000396d  jbe     loc_180003A26
0x180003973  mov     rcx, [rbp+arg_18]
0x180003977  lea     r8, [rbp+arg_10]
0x18000397b  mov     edx, edi
0x18000397d  mov     rax, [rcx]
0x180003980  mov     rax, [rax+20h]
0x180003984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003989  mov     ebx, eax
0x18000398b  test    eax, eax
0x18000398d  js      loc_1800071DC
0x180003993  mov     rcx, [rbp+arg_10]
0x180003997  lea     r8, [rbp+var_10]
0x18000399b  xor     r9d, r9d
0x18000399e  mov     [rsp+40h+var_20], r14
0x1800039a3  lea     rdx, aFileextension; "fileExtension"
0x1800039aa  mov     rax, [rcx]
0x1800039ad  mov     rax, [rax+40h]
0x1800039b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b6  mov     ebx, eax
0x1800039b8  test    eax, eax
0x1800039ba  js      loc_1800071DC
0x1800039c0  mov     rcx, [rbp+arg_10]
0x1800039c4  lea     r8, [rbp+var_8]
0x1800039c8  xor     r9d, r9d
0x1800039cb  mov     [rsp+40h+var_20], r14
0x1800039d0  lea     rdx, aMimetype; "mimeType"
0x1800039d7  mov     rax, [rcx]
0x1800039da  mov     rax, [rax+40h]
0x1800039de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e3  mov     ebx, eax
0x1800039e5  test    eax, eax
0x1800039e7  js      loc_1800071DC
0x1800039ed  mov     r8, [rbp+var_10]; unsigned __int16 *
0x1800039f1  mov     rcx, rsi; this
0x1800039f4  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x1800039f8  call    ?CreateAndAddMimeMapEntry@MIME_MAP_TABLE@@AEAAJPEAG0@Z; MIME_MAP_TABLE::CreateAndAddMimeMapEntry(ushort *,ushort *)
0x1800039fd  mov     ebx, eax
0x1800039ff  test    eax, eax
0x180003a01  js      loc_1800071DC
0x180003a07  mov     rcx, [rbp+arg_10]
0x180003a0b  mov     rax, [rcx]
0x180003a0e  mov     rax, [rax+10h]
0x180003a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a17  inc     edi
0x180003a19  mov     [rbp+arg_10], r14
0x180003a1d  cmp     edi, [rbp+arg_8]
0x180003a20  jb      loc_180003973
0x180003a26  mov     rcx, [rbp+arg_18]
0x180003a2a  mov     rax, [rcx]
0x180003a2d  mov     rax, [rax+10h]
0x180003a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a36  xor     eax, eax
0x180003a38  add     rsp, 40h
0x180003a3c  pop     r14
0x180003a3e  pop     rdi
0x180003a3f  pop     rsi
0x180003a40  pop     rbx
0x180003a41  pop     rbp
0x180003a42  retn
0x1800071dc  mov     rcx, [rbp+arg_10]
0x1800071e0  test    rcx, rcx
0x1800071e3  jz      short loc_1800071F5
0x1800071e5  mov     rax, [rcx]
0x1800071e8  mov     rax, [rax+10h]
0x1800071ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071f1  mov     [rbp+arg_10], r14
0x1800071f5  mov     rcx, [rbp+arg_18]
0x1800071f9  test    rcx, rcx
0x1800071fc  jz      short loc_18000720A
0x1800071fe  mov     rax, [rcx]
0x180007201  mov     rax, [rax+10h]
0x180007205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720a  mov     eax, ebx
0x18000720c  jmp     loc_180003A38
```
