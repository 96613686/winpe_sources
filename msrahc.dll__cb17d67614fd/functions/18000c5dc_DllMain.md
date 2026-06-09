# DllMain

- ea: `0x18000c5dc`
- end: `0x18000c717`
- name: `DllMain`
- size: `315`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800018e4`

## callees

- `0x18000bcdc`
- `0x18000c5dc`
- `0x18001c010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x18000c67c`
- `ADVAPI32!EventRegister` at `0x18000c67c`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000c663`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000c663`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HINSTANCE v3; // rdi
  void (__fastcall **v4)(HINSTANCE, _QWORD, LPVOID); // rbx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v5; // rbx
  __int64 *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v9; // rbx
  __int64 *v10; // rax

  v3 = hinstDLL;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      v4 = (void (__fastcall **)(HINSTANCE, _QWORD, LPVOID))&off_180027000;
      if ( &off_180027000 != (_UNKNOWN *)-1LL )
      {
        qword_1800280C8 = (__int64)&off_180027000;
        if ( off_180027000 )
        {
          do
          {
            LOBYTE(hinstDLL) = 1;
            v4[8](hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
            v4 += 9;
          }
          while ( *v4 );
        }
      }
      v5 = off_180027590;
      v6 = off_180027598;
      while ( v5 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v6 )
      {
        if ( *v5 )
        {
          LOBYTE(hinstDLL) = 1;
          (*((void (__fastcall **)(HINSTANCE))*v5 + 8))(hinstDLL);
          v6 = off_180027598;
        }
        ++v5;
      }
      DisableThreadLibraryCalls(v3);
      EventRegister(&RemoteAssistanceGUID, 0, 0, &g_Logger);
    }
  }
  else
  {
    v7 = qword_1800280C8;
    if ( qword_1800280C8 )
    {
      while ( *(_QWORD *)v7 )
      {
        v8 = *(_QWORD *)(v7 + 32);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        *(_QWORD *)(v7 + 32) = 0;
        (*(void (__fastcall **)(_QWORD))(v7 + 64))(0);
        v7 += 72;
      }
    }
    v9 = off_180027590;
    v10 = off_180027598;
    while ( v9 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v10 )
    {
      if ( *v9 )
      {
        (*((void (__fastcall **)(_QWORD))*v9 + 8))(0);
        v10 = off_180027598;
      }
      ++v9;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&g_AtlModule);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c5dc  mov     [rsp+arg_0], rbx
0x18000c5e1  push    rdi
0x18000c5e2  sub     rsp, 20h
0x18000c5e6  mov     rdi, rcx
0x18000c5e9  test    edx, edx
0x18000c5eb  jz      loc_18000C687
0x18000c5f1  cmp     edx, 1
0x18000c5f4  jnz     loc_18000C707
0x18000c5fa  lea     rbx, off_180027000
0x18000c601  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c605  jz      short loc_18000C62D
0x18000c607  mov     cs:qword_1800280C8, rbx
0x18000c60e  cmp     cs:off_180027000, 0
0x18000c616  jz      short loc_18000C62D
0x18000c618  mov     cl, 1
0x18000c61a  mov     rax, [rbx+40h]
0x18000c61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c623  lea     rbx, [rbx+48h]
0x18000c627  cmp     qword ptr [rbx], 0
0x18000c62b  jnz     short loc_18000C618
0x18000c62d  mov     rbx, cs:off_180027590
0x18000c634  mov     rax, cs:off_180027598
0x18000c63b  jmp     short loc_18000C65B
0x18000c63d  mov     rdx, [rbx]
0x18000c640  test    rdx, rdx
0x18000c643  jz      short loc_18000C657
0x18000c645  mov     cl, 1
0x18000c647  mov     rax, [rdx+40h]
0x18000c64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c650  mov     rax, cs:off_180027598
0x18000c657  add     rbx, 8
0x18000c65b  cmp     rbx, rax
0x18000c65e  jb      short loc_18000C63D
0x18000c660  mov     rcx, rdi; hLibModule
0x18000c663  call    cs:__imp_DisableThreadLibraryCalls
0x18000c669  lea     r9, ?g_Logger@@3VCEventLogger@@A; RegHandle
0x18000c670  xor     r8d, r8d; CallbackContext
0x18000c673  xor     edx, edx; EnableCallback
0x18000c675  lea     rcx, RemoteAssistanceGUID; ProviderId
0x18000c67c  call    cs:__imp_EventRegister
0x18000c682  jmp     loc_18000C707
0x18000c687  mov     rbx, cs:qword_1800280C8
0x18000c68e  test    rbx, rbx
0x18000c691  jz      short loc_18000C6C7
0x18000c693  jmp     short loc_18000C6C1
0x18000c695  mov     rcx, [rbx+20h]
0x18000c699  test    rcx, rcx
0x18000c69c  jz      short loc_18000C6AA
0x18000c69e  mov     rax, [rcx]
0x18000c6a1  mov     rax, [rax+10h]
0x18000c6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6aa  mov     qword ptr [rbx+20h], 0
0x18000c6b2  xor     ecx, ecx
0x18000c6b4  mov     rax, [rbx+40h]
0x18000c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6bd  add     rbx, 48h ; 'H'
0x18000c6c1  cmp     qword ptr [rbx], 0
0x18000c6c5  jnz     short loc_18000C695
0x18000c6c7  mov     rbx, cs:off_180027590
0x18000c6ce  mov     rax, cs:off_180027598
0x18000c6d5  jmp     short loc_18000C6F5
0x18000c6d7  mov     rdx, [rbx]
0x18000c6da  test    rdx, rdx
0x18000c6dd  jz      short loc_18000C6F1
0x18000c6df  xor     ecx, ecx
0x18000c6e1  mov     rax, [rdx+40h]
0x18000c6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ea  mov     rax, cs:off_180027598
0x18000c6f1  add     rbx, 8
0x18000c6f5  cmp     rbx, rax
0x18000c6f8  jb      short loc_18000C6D7
0x18000c6fa  lea     rcx, ?g_AtlModule@@3VCComModule@ATL@@A; this
0x18000c701  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000c706  nop
0x18000c707  mov     eax, 1
0x18000c70c  mov     rbx, [rsp+28h+arg_0]
0x18000c711  add     rsp, 20h
0x18000c715  pop     rdi
0x18000c716  retn
```
