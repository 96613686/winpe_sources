# _LocaleUpdate::_LocaleUpdate(localeinfo_struct *)

- ea: `0x18000d354`
- end: `0x18000d42c`
- name: `??0_LocaleUpdate@@QEAA@PEAUlocaleinfo_struct@@@Z`
- size: `216`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct localeinfo_struct *)`
- caller_count: `34`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d4fc`
- `0x18000d9a4`
- `0x18000e070`
- `0x18000e0bc`
- `0x18000e534`
- `0x18000e89c`
- `0x18000e964`
- `0x18000ed74`
- `0x18000f07c`
- `0x1800143f0`
- `0x1800156a0`
- `0x180016ee8`
- `0x180018390`
- `0x180018508`
- `0x180018f88`
- `0x180019bec`
- `0x180019c7c`
- `0x180019db4`
- `0x180019fd0`
- `0x18001ab68`
- `0x18001b000`
- `0x18001b28c`
- `0x18001b3c8`
- `0x18001c49c`
- `0x18001d09c`
- `0x18001dae0`
- `0x18001def0`
- `0x18001e240`
- `0x18001e640`
- `0x18001e730`
- `0x18001e8b0`
- `0x18001e950`
- `0x18001fa30`
- `0x18001fb1c`

## callees

- `0x18000d354`
- `0x18000f8a4`
- `0x18001557c`
- `0x1800159b4`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct localeinfo_struct *a2)
{
  __int64 v3; // rax
  void *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax

  *((_BYTE *)this + 24) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( a2 )
  {
    *(_OWORD *)this = *(_OWORD *)a2;
  }
  else
  {
    v3 = getptd_noexit();
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v4 = *(void **)(v3 + 192);
      *(_QWORD *)this = v4;
      *((_QWORD *)this + 1) = *(_QWORD *)(v3 + 184);
      if ( v4 != _ptlocinfo && (*(_BYTE *)(v3 + 200) & 2) == 0 && (_globallocalestatus & 1) != 0 )
        *(_QWORD *)this = _updatetlocinfo();
      if ( *((void **)this + 1) != _ptmbcinfo
        && (*(_BYTE *)(*((_QWORD *)this + 2) + 200LL) & 2) == 0
        && (_globallocalestatus & 1) != 0 )
      {
        *((_QWORD *)this + 1) = _updatetmbcinfo();
      }
      v5 = *((_QWORD *)this + 2);
      v6 = *(_DWORD *)(v5 + 200);
      if ( (v6 & 2) == 0 )
      {
        *(_DWORD *)(v5 + 200) = v6 | 2;
        *((_BYTE *)this + 24) = 1;
      }
    }
    else
    {
      *(_QWORD *)this = _ptlocinfo;
      *((_QWORD *)this + 1) = _ptmbcinfo;
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000d354  push    rbx
0x18000d356  sub     rsp, 20h
0x18000d35a  mov     byte ptr [rcx+18h], 0
0x18000d35e  mov     rbx, rcx
0x18000d361  mov     qword ptr [rcx+10h], 0
0x18000d369  test    rdx, rdx
0x18000d36c  jnz     loc_18000D41C
0x18000d372  call    _getptd_noexit
0x18000d377  mov     [rbx+10h], rax
0x18000d37b  test    rax, rax
0x18000d37e  jz      loc_18000D405
0x18000d384  mov     rdx, [rax+0C0h]
0x18000d38b  mov     [rbx], rdx
0x18000d38e  mov     rcx, [rax+0B8h]
0x18000d395  mov     [rbx+8], rcx
0x18000d399  cmp     rdx, cs:__ptlocinfo
0x18000d3a0  jz      short loc_18000D3BC
0x18000d3a2  test    byte ptr [rax+0C8h], 2
0x18000d3a9  jnz     short loc_18000D3BC
0x18000d3ab  test    cs:__globallocalestatus, 1
0x18000d3b2  jz      short loc_18000D3BC
0x18000d3b4  call    __updatetlocinfo
0x18000d3b9  mov     [rbx], rax
0x18000d3bc  mov     rax, cs:__ptmbcinfo
0x18000d3c3  cmp     [rbx+8], rax
0x18000d3c7  jz      short loc_18000D3E8
0x18000d3c9  mov     rax, [rbx+10h]
0x18000d3cd  test    byte ptr [rax+0C8h], 2
0x18000d3d4  jnz     short loc_18000D3E8
0x18000d3d6  test    cs:__globallocalestatus, 1
0x18000d3dd  jz      short loc_18000D3E8
0x18000d3df  call    __updatetmbcinfo
0x18000d3e4  mov     [rbx+8], rax
0x18000d3e8  mov     rcx, [rbx+10h]
0x18000d3ec  mov     eax, [rcx+0C8h]
0x18000d3f2  test    al, 2
0x18000d3f4  jnz     short loc_18000D423
0x18000d3f6  or      eax, 2
0x18000d3f9  mov     [rcx+0C8h], eax
0x18000d3ff  mov     byte ptr [rbx+18h], 1
0x18000d403  jmp     short loc_18000D423
0x18000d405  mov     rax, cs:__ptlocinfo
0x18000d40c  mov     [rbx], rax
0x18000d40f  mov     rax, cs:__ptmbcinfo
0x18000d416  mov     [rbx+8], rax
0x18000d41a  jmp     short loc_18000D423
0x18000d41c  movups  xmm0, xmmword ptr [rdx]
0x18000d41f  movdqu  xmmword ptr [rcx], xmm0
0x18000d423  mov     rax, rbx
0x18000d426  add     rsp, 20h
0x18000d42a  pop     rbx
0x18000d42b  retn
```
