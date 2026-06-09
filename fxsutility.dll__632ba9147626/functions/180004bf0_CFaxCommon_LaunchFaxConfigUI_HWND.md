# CFaxCommon::LaunchFaxConfigUI(HWND__ *)

- ea: `0x180004bf0`
- end: `0x180004c85`
- name: `?LaunchFaxConfigUI@CFaxCommon@@UEAAJPEAUHWND__@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(CFaxCommon *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001284`
- `0x1800012d0`
- `0x180004bf0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CFaxCommon::LaunchFaxConfigUI(CFaxCommon *this, HWND a2)
{
  _QWORD *v3; // rax
  void *v4; // rdi
  HMODULE v5; // rcx
  int v6; // ebx

  v3 = operator new(0x40u);
  v4 = v3;
  if ( v3 )
  {
    v5 = g_hFaxUtilityInst;
    *v3 = &CFaxConfigUI::`vftable';
    v3[1] = v5;
    v3[2] = a2;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    *((_DWORD *)v3 + 12) = 0;
    v3[7] = 0;
    v6 = ((__int64 (__fastcall *)(_QWORD *))CFaxConfigUI::`vftable')(v3);
    operator delete(v4);
    if ( v6 <= 0 )
      return (unsigned int)v6;
  }
  else
  {
    LOWORD(v6) = 8;
  }
  return (unsigned __int16)v6 | 0x80070000;
}

```

## disassembly

```asm
0x180004bf0  mov     [rsp+arg_0], rbx
0x180004bf5  push    rdi
0x180004bf6  sub     rsp, 20h
0x180004bfa  mov     ecx, 40h ; '@'; Size
0x180004bff  mov     rbx, rdx
0x180004c02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c07  mov     rdi, rax
0x180004c0a  test    rax, rax
0x180004c0d  jz      short loc_180004C6A
0x180004c0f  mov     rcx, cs:?g_hFaxUtilityInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hFaxUtilityInst
0x180004c16  lea     rax, ??_7CFaxConfigUI@@6B@; const CFaxConfigUI::`vftable'
0x180004c1d  mov     [rdi], rax
0x180004c20  mov     rax, [rax]
0x180004c23  mov     [rdi+8], rcx
0x180004c27  mov     rcx, rdi
0x180004c2a  mov     [rdi+10h], rbx
0x180004c2e  mov     qword ptr [rdi+18h], 0
0x180004c36  mov     qword ptr [rdi+20h], 0
0x180004c3e  mov     qword ptr [rdi+28h], 0
0x180004c46  mov     dword ptr [rdi+30h], 0
0x180004c4d  mov     qword ptr [rdi+38h], 0
0x180004c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5a  mov     ebx, eax
0x180004c5c  mov     rcx, rdi; Block
0x180004c5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c64  test    ebx, ebx
0x180004c66  jg      short loc_180004C6F
0x180004c68  jmp     short loc_180004C78
0x180004c6a  mov     ebx, 8
0x180004c6f  movzx   ebx, bx
0x180004c72  or      ebx, 80070000h
0x180004c78  mov     eax, ebx
0x180004c7a  mov     rbx, [rsp+28h+arg_0]
0x180004c7f  add     rsp, 20h
0x180004c83  pop     rdi
0x180004c84  retn
```
