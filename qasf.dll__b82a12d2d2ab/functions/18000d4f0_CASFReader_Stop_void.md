# CASFReader::Stop(void)

- ea: `0x18000d4f0`
- end: `0x18000d54a`
- name: `?Stop@CASFReader@@UEAAJXZ`
- size: `90`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006b08`
- `0x180008764`
- `0x18000d4f0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::Stop(CASFReader *this)
{
  __int64 v1; // rdx
  CASFReader *v3; // rcx

  v1 = *((_QWORD *)this + 55);
  v3 = (CASFReader *)((char *)this - 24);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 32LL))(v1);
  if ( !*((_QWORD *)this + 40) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 4) )
    CASFReader::CallStop(v3);
  return CBaseFilter::Stop(this);
}

```

## disassembly

```asm
0x18000d4f0  push    rbx
0x18000d4f2  sub     rsp, 20h
0x18000d4f6  mov     rdx, [rcx+1B8h]
0x18000d4fd  mov     rbx, rcx
0x18000d500  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000d504  test    rdx, rdx
0x18000d507  jz      short loc_18000D51D
0x18000d509  mov     rax, [rdx]
0x18000d50c  mov     rcx, rdx
0x18000d50f  mov     rax, [rax+20h]
0x18000d513  add     rsp, 20h
0x18000d517  pop     rbx
0x18000d518  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d51d  cmp     qword ptr [rbx+140h], 0
0x18000d525  jnz     short loc_18000D532
0x18000d527  mov     eax, 80004005h
0x18000d52c  add     rsp, 20h
0x18000d530  pop     rbx
0x18000d531  retn
0x18000d532  cmp     dword ptr [rbx+10h], 0
0x18000d536  jz      short loc_18000D53D
0x18000d538  call    ?CallStop@CASFReader@@AEAAJXZ; CASFReader::CallStop(void)
0x18000d53d  mov     rcx, rbx; this
0x18000d540  add     rsp, 20h
0x18000d544  pop     rbx
0x18000d545  jmp     ?Stop@CBaseFilter@@UEAAJXZ; CBaseFilter::Stop(void)
```
