# DllMain

- ea: `0x18000a0b4`
- end: `0x18000a2cf`
- name: `DllMain`
- size: `539`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800017c4`

## callees

- `0x1800097ec`
- `0x18000a0b4`
- `0x18000a45c`
- `0x18000a558`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a14b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a14b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a158`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a158`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1d1`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000a222`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000a222`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rcx
  void (__fastcall **v5)(_QWORD); // rbx
  __int64 *v6; // rbx
  __int64 *v7; // rax
  PVOID *v8; // rbx
  TRACEHANDLE v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rbx
  __int64 *v13; // rax

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_18003BC38 = 0;
      WPP_MAIN_CB = 0;
      qword_18003BC40 = 1;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WppInitUm(hinstDLL, fdwReason, lpvReserved);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids);
      }
      DisableThreadLibraryCalls(hinstDLL);
      InitializeCriticalSection(&g_CritSec);
      v5 = (void (__fastcall **)(_QWORD))&off_18003B000;
      if ( &off_18003B000 != (_UNKNOWN *)-1LL )
      {
        qword_18003BCA8 = (__int64)&off_18003B000;
        if ( off_18003B000 )
        {
          do
          {
            LOBYTE(v4) = 1;
            v5[8](v4);
            v5 += 9;
          }
          while ( *v5 );
        }
      }
      v6 = off_18003B120[0];
      v7 = off_18003B128;
      while ( v6 < v7 )
      {
        if ( *v6 )
        {
          LOBYTE(v4) = 1;
          (*(void (__fastcall **)(__int64))(*v6 + 64))(v4);
          v7 = off_18003B128;
        }
        ++v6;
      }
    }
  }
  else
  {
    DeleteCriticalSection(&g_CritSec);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control )
      {
        while ( v8 )
        {
          v9 = (TRACEHANDLE)v8[1];
          if ( v9 )
          {
            UnregisterTraceGuids(v9);
            v8[1] = 0;
          }
          v8 = (PVOID *)*v8;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
    v10 = qword_18003BCA8;
    if ( qword_18003BCA8 )
    {
      while ( *(_QWORD *)v10 )
      {
        v11 = *(_QWORD *)(v10 + 32);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *(_QWORD *)(v10 + 32) = 0;
        (*(void (__fastcall **)(_QWORD))(v10 + 64))(0);
        v10 += 72;
      }
    }
    v12 = off_18003B120[0];
    v13 = off_18003B128;
    while ( v12 < v13 )
    {
      if ( *v12 )
      {
        (*(void (__fastcall **)(_QWORD))(*v12 + 64))(0);
        v13 = off_18003B128;
      }
      ++v12;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a0b4  mov     [rsp+arg_0], rbx
0x18000a0b9  push    rdi
0x18000a0ba  sub     rsp, 20h
0x18000a0be  mov     rbx, rcx
0x18000a0c1  test    edx, edx
0x18000a0c3  jz      loc_18000A1CA
0x18000a0c9  cmp     edx, 1
0x18000a0cc  jnz     loc_18000A2BF
0x18000a0d2  mov     cs:qword_18003BC38, 0
0x18000a0dd  mov     cs:WPP_MAIN_CB, 0
0x18000a0e8  mov     cs:qword_18003BC40, 1
0x18000a0f3  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18000a0fa  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000a101  lea     rax, WPP_MAIN_CB
0x18000a108  mov     cs:WPP_GLOBAL_Control, rax
0x18000a10f  call    WppInitUm
0x18000a114  lea     rdi, WPP_GLOBAL_Control
0x18000a11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a122  cmp     rcx, rdi
0x18000a125  jz      short loc_18000A148
0x18000a127  test    byte ptr [rcx+1Ch], 8
0x18000a12b  jz      short loc_18000A148
0x18000a12d  cmp     byte ptr [rcx+19h], 4
0x18000a131  jb      short loc_18000A148
0x18000a133  mov     edx, 0Ah
0x18000a138  lea     r8, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids
0x18000a13f  mov     rcx, [rcx+10h]
0x18000a143  call    WPP_SF_
0x18000a148  mov     rcx, rbx; hLibModule
0x18000a14b  call    cs:__imp_DisableThreadLibraryCalls
0x18000a151  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a158  call    cs:__imp_InitializeCriticalSection
0x18000a15e  nop
0x18000a15f  lea     rbx, off_18003B000
0x18000a166  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a16a  jz      short loc_18000A192
0x18000a16c  mov     cs:qword_18003BCA8, rbx
0x18000a173  cmp     cs:off_18003B000, 0
0x18000a17b  jz      short loc_18000A192
0x18000a17d  mov     cl, 1
0x18000a17f  mov     rax, [rbx+40h]
0x18000a183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a188  lea     rbx, [rbx+48h]
0x18000a18c  cmp     qword ptr [rbx], 0
0x18000a190  jnz     short loc_18000A17D
0x18000a192  mov     rbx, cs:off_18003B120
0x18000a199  mov     rax, cs:off_18003B128
0x18000a1a0  jmp     short loc_18000A1C0
0x18000a1a2  mov     rdx, [rbx]
0x18000a1a5  test    rdx, rdx
0x18000a1a8  jz      short loc_18000A1BC
0x18000a1aa  mov     cl, 1
0x18000a1ac  mov     rax, [rdx+40h]
0x18000a1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b5  mov     rax, cs:off_18003B128
0x18000a1bc  add     rbx, 8
0x18000a1c0  cmp     rbx, rax
0x18000a1c3  jb      short loc_18000A1A2
0x18000a1c5  jmp     loc_18000A2BF
0x18000a1ca  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a1d1  call    cs:__imp_DeleteCriticalSection
0x18000a1d7  lea     rdi, WPP_GLOBAL_Control
0x18000a1de  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a1e5  cmp     rbx, rdi
0x18000a1e8  jz      short loc_18000A23F
0x18000a1ea  test    byte ptr [rbx+1Ch], 8
0x18000a1ee  jz      short loc_18000A212
0x18000a1f0  cmp     byte ptr [rbx+19h], 4
0x18000a1f4  jb      short loc_18000A212
0x18000a1f6  mov     edx, 0Ch
0x18000a1fb  lea     r8, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids
0x18000a202  mov     rcx, [rbx+10h]
0x18000a206  call    WPP_SF_
0x18000a20b  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a212  cmp     rbx, rdi
0x18000a215  jz      short loc_18000A23F
0x18000a217  jmp     short loc_18000A233
0x18000a219  mov     rcx, [rbx+8]; RegistrationHandle
0x18000a21d  test    rcx, rcx
0x18000a220  jz      short loc_18000A230
0x18000a222  call    cs:__imp_UnregisterTraceGuids
0x18000a228  mov     qword ptr [rbx+8], 0
0x18000a230  mov     rbx, [rbx]
0x18000a233  test    rbx, rbx
0x18000a236  jnz     short loc_18000A219
0x18000a238  mov     cs:WPP_GLOBAL_Control, rdi
0x18000a23f  mov     rbx, cs:qword_18003BCA8
0x18000a246  test    rbx, rbx
0x18000a249  jz      short loc_18000A27F
0x18000a24b  jmp     short loc_18000A279
0x18000a24d  mov     rcx, [rbx+20h]
0x18000a251  test    rcx, rcx
0x18000a254  jz      short loc_18000A262
0x18000a256  mov     rax, [rcx]
0x18000a259  mov     rax, [rax+10h]
0x18000a25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a262  mov     qword ptr [rbx+20h], 0
0x18000a26a  xor     ecx, ecx
0x18000a26c  mov     rax, [rbx+40h]
0x18000a270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a275  add     rbx, 48h ; 'H'
0x18000a279  cmp     qword ptr [rbx], 0
0x18000a27d  jnz     short loc_18000A24D
0x18000a27f  mov     rbx, cs:off_18003B120
0x18000a286  mov     rax, cs:off_18003B128
0x18000a28d  jmp     short loc_18000A2AD
0x18000a28f  mov     rdx, [rbx]
0x18000a292  test    rdx, rdx
0x18000a295  jz      short loc_18000A2A9
0x18000a297  xor     ecx, ecx
0x18000a299  mov     rax, [rdx+40h]
0x18000a29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a2  mov     rax, cs:off_18003B128
0x18000a2a9  add     rbx, 8
0x18000a2ad  cmp     rbx, rax
0x18000a2b0  jb      short loc_18000A28F
0x18000a2b2  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000a2b9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000a2be  nop
0x18000a2bf  mov     eax, 1
0x18000a2c4  mov     rbx, [rsp+28h+arg_0]
0x18000a2c9  add     rsp, 20h
0x18000a2cd  pop     rdi
0x18000a2ce  retn
```
