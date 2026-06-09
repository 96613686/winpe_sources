# CDirectMusicEmulateInPort::ActivateLegacyDevice(int)

- ea: `0x18001c500`
- end: `0x18001c6ce`
- name: `?ActivateLegacyDevice@CDirectMusicEmulateInPort@@UEAAJH@Z`
- size: `462`
- prototype: `__int64 __fastcall(CDirectMusicEmulateInPort *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001b808`
- `0x18001c500`
- `0x18001ca1c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c65a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c65a`
- `api-ms-win-mm-mme-l1-1-0!midiInReset` at `0x18001c635`
- `api-ms-win-mm-mme-l1-1-0!midiInReset` at `0x18001c635`
- `api-ms-win-mm-mme-l1-1-0!midiInStart` at `0x18001c58c`
- `api-ms-win-mm-mme-l1-1-0!midiInStart` at `0x18001c58c`
- `api-ms-win-mm-mme-l1-1-0!midiInClose` at `0x18001c6a6`
- `api-ms-win-mm-mme-l1-1-0!midiInClose` at `0x18001c6a6`
- `api-ms-win-mm-mme-l1-1-0!midiInUnprepareHeader` at `0x18001c694`
- `api-ms-win-mm-mme-l1-1-0!midiInUnprepareHeader` at `0x18001c694`
- `api-ms-win-mm-mme-l1-1-0!midiInOpen` at `0x18001c53c`
- `api-ms-win-mm-mme-l1-1-0!midiInOpen` at `0x18001c53c`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulateInPort::ActivateLegacyDevice(CDirectMusicEmulateInPort *this, int a2)
{
  HMIDIIN *v2; // rsi
  MMRESULT v4; // eax
  int v5; // edi
  MMRESULT v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  MMRESULT v9; // eax
  int v10; // edi
  __int64 i; // rdi
  MMRESULT v12; // eax
  __int64 v14; // [rsp+50h] [rbp+18h] BYREF
  __int64 v15; // [rsp+58h] [rbp+20h] BYREF

  v2 = (HMIDIIN *)((char *)this + 512);
  if ( a2 )
  {
    v4 = midiInOpen((LPHMIDIIN)this + 64, *((_DWORD *)this + 94), (DWORD_PTR)&midiInProc, (DWORD_PTR)this, 0x30000u);
    v5 = MMRESULTToHRESULT(v4);
    if ( v5 < 0 )
      goto LABEL_11;
    v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 48) + 24LL))(
           *((_QWORD *)this + 48),
           (char *)this + 520);
    if ( v5 < 0 )
      goto LABEL_11;
    v5 = CDirectMusicEmulateInPort::PostSysExBuffers(this);
    if ( v5 < 0 )
      goto LABEL_11;
    v6 = midiInStart(*v2);
    v5 = MMRESULTToHRESULT(v6);
    if ( v5 < 0 )
      goto LABEL_11;
    if ( *((_QWORD *)this + 4310) )
    {
      v7 = *((_QWORD *)this + 48);
      v14 = 0;
      v15 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, &v14);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 4310) + 24LL))(
               *((_QWORD *)this + 4310),
               &v15);
        if ( v8 >= 0 )
        {
          *((_QWORD *)this + 4309) = v14 - v15;
          return (unsigned int)v5;
        }
      }
      v5 = v8;
LABEL_11:
      (*(void (__fastcall **)(CDirectMusicEmulateInPort *, _QWORD))(*(_QWORD *)this + 184LL))(this, 0);
    }
  }
  else
  {
    *((_DWORD *)this + 132) = 1;
    v9 = midiInReset(*v2);
    if ( v9 )
    {
      v5 = MMRESULTToHRESULT(v9);
      if ( v5 < 0 )
        return (unsigned int)v5;
    }
    else
    {
      v10 = 500;
      do
      {
        if ( !*((_DWORD *)this + 133) )
          break;
        Sleep(0xAu);
        --v10;
      }
      while ( v10 );
      for ( i = 0; i != 8; ++i )
      {
        if ( (*((_BYTE *)this + 4240 * i + 588) & 2) != 0 )
          midiInUnprepareHeader(*v2, (LPMIDIHDR)((char *)this + 4240 * i + 564), 0x70u);
      }
    }
    v12 = midiInClose(*v2);
    v5 = MMRESULTToHRESULT(v12);
    *v2 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c500  mov     [rsp+arg_0], rbx
0x18001c505  mov     [rsp+arg_8], rsi
0x18001c50a  push    rdi
0x18001c50b  sub     rsp, 30h
0x18001c50f  lea     rsi, [rcx+200h]
0x18001c516  mov     rbx, rcx
0x18001c519  test    edx, edx
0x18001c51b  jz      loc_18001C628
0x18001c521  mov     edx, [rcx+178h]; uDeviceID
0x18001c527  lea     r8, midiInProc; dwCallback
0x18001c52e  mov     r9, rcx; dwInstance
0x18001c531  mov     [rsp+38h+fdwOpen], 30000h; fdwOpen
0x18001c539  mov     rcx, rsi; phmi
0x18001c53c  call    cs:__imp_midiInOpen
0x18001c542  mov     ecx, eax; unsigned int
0x18001c544  call    ?MMRESULTToHRESULT@@YAJI@Z; MMRESULTToHRESULT(uint)
0x18001c549  mov     edi, eax
0x18001c54b  test    eax, eax
0x18001c54d  js      loc_18001C60F
0x18001c553  mov     rcx, [rbx+180h]
0x18001c55a  lea     rdx, [rbx+208h]
0x18001c561  mov     rax, [rcx]
0x18001c564  mov     rax, [rax+18h]
0x18001c568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c56d  mov     edi, eax
0x18001c56f  test    eax, eax
0x18001c571  js      loc_18001C60F
0x18001c577  mov     rcx, rbx; this
0x18001c57a  call    ?PostSysExBuffers@CDirectMusicEmulateInPort@@AEAAJXZ; CDirectMusicEmulateInPort::PostSysExBuffers(void)
0x18001c57f  mov     edi, eax
0x18001c581  test    eax, eax
0x18001c583  js      loc_18001C60F
0x18001c589  mov     rcx, [rsi]; hmi
0x18001c58c  call    cs:__imp_midiInStart
0x18001c592  mov     ecx, eax; unsigned int
0x18001c594  call    ?MMRESULTToHRESULT@@YAJI@Z; MMRESULTToHRESULT(uint)
0x18001c599  mov     edi, eax
0x18001c59b  test    eax, eax
0x18001c59d  js      short loc_18001C60F
0x18001c59f  cmp     qword ptr [rbx+86B0h], 0
0x18001c5a7  jz      loc_18001C6BC
0x18001c5ad  mov     rcx, [rbx+180h]
0x18001c5b4  lea     rdx, [rsp+38h+arg_10]
0x18001c5b9  mov     [rsp+38h+arg_10], 0
0x18001c5c2  mov     [rsp+38h+arg_18], 0
0x18001c5cb  mov     rax, [rcx]
0x18001c5ce  mov     rax, [rax+18h]
0x18001c5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5d7  test    eax, eax
0x18001c5d9  js      short loc_18001C60D
0x18001c5db  mov     rcx, [rbx+86B0h]
0x18001c5e2  lea     rdx, [rsp+38h+arg_18]
0x18001c5e7  mov     rax, [rcx]
0x18001c5ea  mov     rax, [rax+18h]
0x18001c5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5f3  test    eax, eax
0x18001c5f5  js      short loc_18001C60D
0x18001c5f7  mov     rax, [rsp+38h+arg_10]
0x18001c5fc  sub     rax, [rsp+38h+arg_18]
0x18001c601  mov     [rbx+86A8h], rax
0x18001c608  jmp     loc_18001C6BC
0x18001c60d  mov     edi, eax
0x18001c60f  mov     rax, [rbx]
0x18001c612  xor     edx, edx
0x18001c614  mov     rcx, rbx
0x18001c617  mov     rax, [rax+0B8h]
0x18001c61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c623  jmp     loc_18001C6BC
0x18001c628  mov     dword ptr [rcx+210h], 1
0x18001c632  mov     rcx, [rsi]; hmi
0x18001c635  call    cs:__imp_midiInReset
0x18001c63b  test    eax, eax
0x18001c63d  jz      short loc_18001C64E
0x18001c63f  mov     ecx, eax; unsigned int
0x18001c641  call    ?MMRESULTToHRESULT@@YAJI@Z; MMRESULTToHRESULT(uint)
0x18001c646  mov     edi, eax
0x18001c648  test    eax, eax
0x18001c64a  jns     short loc_18001C6A3
0x18001c64c  jmp     short loc_18001C6BC
0x18001c64e  mov     edi, 1F4h
0x18001c653  jmp     short loc_18001C665
0x18001c655  mov     ecx, 0Ah; dwMilliseconds
0x18001c65a  call    cs:__imp_Sleep
0x18001c660  sub     edi, 1
0x18001c663  jz      short loc_18001C66E
0x18001c665  cmp     dword ptr [rbx+214h], 0
0x18001c66c  jnz     short loc_18001C655
0x18001c66e  xor     edi, edi
0x18001c670  imul    rax, rdi, 1090h
0x18001c677  test    byte ptr [rax+rbx+24Ch], 2
0x18001c67f  jz      short loc_18001C69A
0x18001c681  mov     rcx, [rsi]; hmi
0x18001c684  lea     rdx, [rbx+234h]
0x18001c68b  add     rdx, rax; pmh
0x18001c68e  mov     r8d, 70h ; 'p'; cbmh
0x18001c694  call    cs:__imp_midiInUnprepareHeader
0x18001c69a  inc     rdi
0x18001c69d  cmp     rdi, 8
0x18001c6a1  jnz     short loc_18001C670
0x18001c6a3  mov     rcx, [rsi]; hmi
0x18001c6a6  call    cs:__imp_midiInClose
0x18001c6ac  mov     ecx, eax; unsigned int
0x18001c6ae  call    ?MMRESULTToHRESULT@@YAJI@Z; MMRESULTToHRESULT(uint)
0x18001c6b3  mov     edi, eax
0x18001c6b5  mov     qword ptr [rsi], 0
0x18001c6bc  mov     rbx, [rsp+38h+arg_0]
0x18001c6c1  mov     eax, edi
0x18001c6c3  mov     rsi, [rsp+38h+arg_8]
0x18001c6c8  add     rsp, 30h
0x18001c6cc  pop     rdi
0x18001c6cd  retn
```
