# _LocaleUpdate::_LocaleUpdate(localeinfo_struct *)

- ea: `0x180001038`
- end: `0x180001110`
- name: `??0_LocaleUpdate@@QEAA@PEAUlocaleinfo_struct@@@Z`
- size: `216`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct localeinfo_struct *)`
- caller_count: `192`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180001120`
- `0x180001180`
- `0x180001320`
- `0x180001390`
- `0x180001400`
- `0x180001470`
- `0x1800014e0`
- `0x180001550`
- `0x1800015c0`
- `0x180001630`
- `0x1800016a0`
- `0x180001710`
- `0x180001780`
- `0x180001820`
- `0x1800018c0`
- `0x180001950`
- `0x1800019e0`
- `0x180001a80`
- `0x180001b10`
- `0x180001bb0`
- `0x180001c40`
- `0x180001cd0`
- `0x180001d60`
- `0x180001e10`
- `0x180001f00`
- `0x180002000`
- `0x180002190`
- `0x180002230`
- `0x180002770`
- `0x180003330`
- `0x1800034e0`
- `0x180003600`
- `0x180003770`
- `0x18000389c`
- `0x180003a80`
- `0x180003c50`
- `0x180003d20`
- `0x180003e40`
- `0x180003f80`
- `0x180004140`
- `0x18000447c`
- `0x1800048b0`
- `0x180004a50`
- `0x180004bd0`
- `0x180004cc0`
- `0x180004dc0`
- `0x180004f70`
- `0x1800052f4`
- `0x18000568c`
- `0x180005ad0`

## callees

- `0x180001038`
- `0x180024294`
- `0x18002c214`
- `0x18003e074`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct localeinfo_struct *a2)
{
  __int64 v3; // rax
  struct threadlocaleinfostruct *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax

  *((_BYTE *)this + 24) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( a2 )
  {
    *(struct localeinfo_struct *)this = *a2;
  }
  else
  {
    v3 = getptd_noexit();
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v4 = *(struct threadlocaleinfostruct **)(v3 + 192);
      *(_QWORD *)this = v4;
      *((_QWORD *)this + 1) = *(_QWORD *)(v3 + 184);
      if ( v4 != _ptlocinfo && (*(_BYTE *)(v3 + 200) & 2) == 0 && (_globallocalestatus & 1) != 0 )
        *(_QWORD *)this = _updatetlocinfo();
      if ( *((pthreadmbcinfo *)this + 1) != _ptmbcinfo
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
0x180001038  push    rbx
0x18000103a  sub     rsp, 20h
0x18000103e  mov     byte ptr [rcx+18h], 0
0x180001042  mov     rbx, rcx
0x180001045  mov     qword ptr [rcx+10h], 0
0x18000104d  test    rdx, rdx
0x180001050  jnz     loc_180001100
0x180001056  call    _getptd_noexit
0x18000105b  mov     [rbx+10h], rax
0x18000105f  test    rax, rax
0x180001062  jz      loc_1800010E9
0x180001068  mov     rdx, [rax+0C0h]
0x18000106f  mov     [rbx], rdx
0x180001072  mov     rcx, [rax+0B8h]
0x180001079  mov     [rbx+8], rcx
0x18000107d  cmp     rdx, cs:__ptlocinfo
0x180001084  jz      short loc_1800010A0
0x180001086  test    byte ptr [rax+0C8h], 2
0x18000108d  jnz     short loc_1800010A0
0x18000108f  test    byte ptr cs:__globallocalestatus, 1
0x180001096  jz      short loc_1800010A0
0x180001098  call    __updatetlocinfo
0x18000109d  mov     [rbx], rax
0x1800010a0  mov     rax, cs:__ptmbcinfo
0x1800010a7  cmp     [rbx+8], rax
0x1800010ab  jz      short loc_1800010CC
0x1800010ad  mov     rax, [rbx+10h]
0x1800010b1  test    byte ptr [rax+0C8h], 2
0x1800010b8  jnz     short loc_1800010CC
0x1800010ba  test    byte ptr cs:__globallocalestatus, 1
0x1800010c1  jz      short loc_1800010CC
0x1800010c3  call    __updatetmbcinfo
0x1800010c8  mov     [rbx+8], rax
0x1800010cc  mov     rcx, [rbx+10h]
0x1800010d0  mov     eax, [rcx+0C8h]
0x1800010d6  test    al, 2
0x1800010d8  jnz     short loc_180001107
0x1800010da  or      eax, 2
0x1800010dd  mov     [rcx+0C8h], eax
0x1800010e3  mov     byte ptr [rbx+18h], 1
0x1800010e7  jmp     short loc_180001107
0x1800010e9  mov     rax, cs:__ptlocinfo
0x1800010f0  mov     [rbx], rax
0x1800010f3  mov     rax, cs:__ptmbcinfo
0x1800010fa  mov     [rbx+8], rax
0x1800010fe  jmp     short loc_180001107
0x180001100  movups  xmm0, xmmword ptr [rdx]
0x180001103  movdqu  xmmword ptr [rcx], xmm0
0x180001107  mov     rax, rbx
0x18000110a  add     rsp, 20h
0x18000110e  pop     rbx
0x18000110f  retn
```
