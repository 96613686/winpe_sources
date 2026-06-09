# ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)

- ea: `0x18000a47c`
- end: `0x18000a4f0`
- name: `?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001160`

## callees

- `0x18000a47c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::Init(
        ATL::CComModule *this,
        struct ATL::_ATL_OBJMAP_ENTRY30 *a2,
        HINSTANCE a3,
        const struct _GUID *a4)
{
  void (__fastcall **v4)(ATL::CComModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *); // rbx
  __int64 *v5; // rbx
  __int64 *v6; // rax

  v4 = (void (__fastcall **)(ATL::CComModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *))&off_180012000;
  if ( &off_180012000 != (_UNKNOWN *)-1LL )
  {
    qword_180012928 = (__int64)&off_180012000;
    if ( off_180012000 )
    {
      do
      {
        LOBYTE(this) = 1;
        v4[8](this, a2, a3, a4);
        v4 += 9;
      }
      while ( *v4 );
    }
  }
  v5 = (__int64 *)off_1800121B0[0];
  v6 = (__int64 *)off_1800121B8;
  while ( v5 < v6 )
  {
    if ( *v5 )
    {
      LOBYTE(this) = 1;
      (*(void (__fastcall **)(ATL::CComModule *))(*v5 + 64))(this);
      v6 = (__int64 *)off_1800121B8;
    }
    ++v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a47c  push    rbx
0x18000a47e  sub     rsp, 20h
0x18000a482  lea     rbx, off_180012000
0x18000a489  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a48d  jz      short loc_18000A4B5
0x18000a48f  mov     cs:qword_180012928, rbx
0x18000a496  cmp     cs:off_180012000, 0
0x18000a49e  jz      short loc_18000A4B5
0x18000a4a0  mov     cl, 1
0x18000a4a2  mov     rax, [rbx+40h]
0x18000a4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ab  lea     rbx, [rbx+48h]
0x18000a4af  cmp     qword ptr [rbx], 0
0x18000a4b3  jnz     short loc_18000A4A0
0x18000a4b5  mov     rbx, cs:off_1800121B0
0x18000a4bc  mov     rax, cs:off_1800121B8
0x18000a4c3  jmp     short loc_18000A4E3
0x18000a4c5  mov     rdx, [rbx]
0x18000a4c8  test    rdx, rdx
0x18000a4cb  jz      short loc_18000A4DF
0x18000a4cd  mov     cl, 1
0x18000a4cf  mov     rax, [rdx+40h]
0x18000a4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d8  mov     rax, cs:off_1800121B8
0x18000a4df  add     rbx, 8
0x18000a4e3  cmp     rbx, rax
0x18000a4e6  jb      short loc_18000A4C5
0x18000a4e8  xor     eax, eax
0x18000a4ea  add     rsp, 20h
0x18000a4ee  pop     rbx
0x18000a4ef  retn
```
