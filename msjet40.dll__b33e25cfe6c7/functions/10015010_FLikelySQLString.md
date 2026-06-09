# FLikelySQLString

- ea: `0x10015010`
- end: `0x1001532f`
- name: `FLikelySQLString`
- size: `799`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10015340`
- `0x10015460`

## callees

- `0x100129b0`
- `0x10015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015023`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015057`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015081`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100150ab`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100150d5`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100150ff`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015129`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015153`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001517d`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151a7`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151d1`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151fb`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015225`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001524f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015279`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152a3`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152c9`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152ef`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015315`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015023`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015057`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015081`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100150ab`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100150d5`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100150ff`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015129`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015153`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001517d`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151a7`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151d1`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151fb`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015225`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001524f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015279`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152a3`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152c9`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152ef`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015315`

## string_xrefs

- `0x10015166`: `update`
- `0x100150be`: `commit`
- `0x1001513c`: `delete`
- `0x10015262`: `create`
- `0x100150e8`: `rollback`

## pseudocode

```c
BOOL __thiscall FLikelySQLString(wint_t *this)
{
  wint_t *v1; // esi
  wint_t v2; // cx
  wint_t v3; // ax

  v1 = this;
  if ( *this )
  {
    v2 = *this;
    do
    {
      if ( !_iswctype(v2, 8u) )
        break;
      v3 = v1[1];
      ++v1;
      v2 = v3;
    }
    while ( v3 );
  }
  return !WCSNICMP(5) && _iswctype(v1[5], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(5) && _iswctype(v1[5], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(8) && _iswctype(v1[8], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(7) && _iswctype(v1[7], 8u)
      || !WCSNICMP(4) && _iswctype(v1[4], 8u)
      || !WCSNICMP(9) && _iswctype(v1[9], 8u)
      || !WCSNICMP(5) && _iswctype(v1[5], 8u)
      || !WCSNICMP(6) && _iswctype(v1[6], 8u)
      || !WCSNICMP(4) && _iswctype(v1[4], 8u)
      || !WCSNICMP(9) && _iswctype(v1[9], 8u)
      || !WCSNICMP(10) && _iswctype(v1[10], 8u)
      || !WCSNICMP(3) && _iswctype(v1[3], 8u);
}

```

## disassembly

```asm
0x10015010  mov     edi, edi
0x10015012  push    esi
0x10015013  mov     esi, ecx
0x10015015  push    edi
0x10015016  movzx   eax, word ptr [esi]
0x10015019  test    ax, ax
0x1001501c  jz      short loc_1001503E
0x1001501e  mov     ecx, eax
0x10015020  push    8; Type
0x10015022  push    ecx; C
0x10015023  call    ds:__imp__iswctype
0x10015029  add     esp, 8
0x1001502c  test    eax, eax
0x1001502e  jz      short loc_1001503E
0x10015030  movzx   eax, word ptr [esi+2]
0x10015034  add     esi, 2
0x10015037  mov     ecx, eax
0x10015039  test    ax, ax
0x1001503c  jnz     short loc_10015020
0x1001503e  push    5
0x10015040  mov     edx, offset aGrant; "grant"
0x10015045  mov     ecx, esi
0x10015047  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001504c  test    eax, eax
0x1001504e  jnz     short loc_10015068
0x10015050  movzx   eax, word ptr [esi+0Ah]
0x10015054  push    8; Type
0x10015056  push    eax; C
0x10015057  call    ds:__imp__iswctype
0x1001505d  add     esp, 8
0x10015060  test    eax, eax
0x10015062  jnz     loc_10015322
0x10015068  push    6
0x1001506a  mov     edx, offset aRevoke; "revoke"
0x1001506f  mov     ecx, esi
0x10015071  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015076  test    eax, eax
0x10015078  jnz     short loc_10015092
0x1001507a  movzx   eax, word ptr [esi+0Ch]
0x1001507e  push    8; Type
0x10015080  push    eax; C
0x10015081  call    ds:__imp__iswctype
0x10015087  add     esp, 8
0x1001508a  test    eax, eax
0x1001508c  jnz     loc_10015322
0x10015092  push    5
0x10015094  mov     edx, offset aBegin; "begin"
0x10015099  mov     ecx, esi
0x1001509b  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100150a0  test    eax, eax
0x100150a2  jnz     short loc_100150BC
0x100150a4  movzx   eax, word ptr [esi+0Ah]
0x100150a8  push    8; Type
0x100150aa  push    eax; C
0x100150ab  call    ds:__imp__iswctype
0x100150b1  add     esp, 8
0x100150b4  test    eax, eax
0x100150b6  jnz     loc_10015322
0x100150bc  push    6
0x100150be  mov     edx, offset aCommit; "commit"
0x100150c3  mov     ecx, esi
0x100150c5  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100150ca  test    eax, eax
0x100150cc  jnz     short loc_100150E6
0x100150ce  movzx   eax, word ptr [esi+0Ch]
0x100150d2  push    8; Type
0x100150d4  push    eax; C
0x100150d5  call    ds:__imp__iswctype
0x100150db  add     esp, 8
0x100150de  test    eax, eax
0x100150e0  jnz     loc_10015322
0x100150e6  push    8
0x100150e8  mov     edx, offset aRollback; "rollback"
0x100150ed  mov     ecx, esi
0x100150ef  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100150f4  test    eax, eax
0x100150f6  jnz     short loc_10015110
0x100150f8  movzx   eax, word ptr [esi+10h]
0x100150fc  push    8; Type
0x100150fe  push    eax; C
0x100150ff  call    ds:__imp__iswctype
0x10015105  add     esp, 8
0x10015108  test    eax, eax
0x1001510a  jnz     loc_10015322
0x10015110  push    6
0x10015112  mov     edx, offset aSelect_0; "select"
0x10015117  mov     ecx, esi
0x10015119  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001511e  test    eax, eax
0x10015120  jnz     short loc_1001513A
0x10015122  movzx   eax, word ptr [esi+0Ch]
0x10015126  push    8; Type
0x10015128  push    eax; C
0x10015129  call    ds:__imp__iswctype
0x1001512f  add     esp, 8
0x10015132  test    eax, eax
0x10015134  jnz     loc_10015322
0x1001513a  push    6
0x1001513c  mov     edx, offset aDelete; "delete"
0x10015141  mov     ecx, esi
0x10015143  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015148  test    eax, eax
0x1001514a  jnz     short loc_10015164
0x1001514c  movzx   eax, word ptr [esi+0Ch]
0x10015150  push    8; Type
0x10015152  push    eax; C
0x10015153  call    ds:__imp__iswctype
0x10015159  add     esp, 8
0x1001515c  test    eax, eax
0x1001515e  jnz     loc_10015322
0x10015164  push    6
0x10015166  mov     edx, offset aUpdate; "update"
0x1001516b  mov     ecx, esi
0x1001516d  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015172  test    eax, eax
0x10015174  jnz     short loc_1001518E
0x10015176  movzx   eax, word ptr [esi+0Ch]
0x1001517a  push    8; Type
0x1001517c  push    eax; C
0x1001517d  call    ds:__imp__iswctype
0x10015183  add     esp, 8
0x10015186  test    eax, eax
0x10015188  jnz     loc_10015322
0x1001518e  push    6
0x10015190  mov     edx, offset aInsert; "insert"
0x10015195  mov     ecx, esi
0x10015197  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001519c  test    eax, eax
0x1001519e  jnz     short loc_100151B8
0x100151a0  movzx   eax, word ptr [esi+0Ch]
0x100151a4  push    8; Type
0x100151a6  push    eax; C
0x100151a7  call    ds:__imp__iswctype
0x100151ad  add     esp, 8
0x100151b0  test    eax, eax
0x100151b2  jnz     loc_10015322
0x100151b8  push    7
0x100151ba  mov     edx, offset aExecute; "execute"
0x100151bf  mov     ecx, esi
0x100151c1  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100151c6  test    eax, eax
0x100151c8  jnz     short loc_100151E2
0x100151ca  movzx   eax, word ptr [esi+0Eh]
0x100151ce  push    8; Type
0x100151d0  push    eax; C
0x100151d1  call    ds:__imp__iswctype
0x100151d7  add     esp, 8
0x100151da  test    eax, eax
0x100151dc  jnz     loc_10015322
0x100151e2  push    4
0x100151e4  mov     edx, offset aExec_0; "exec"
0x100151e9  mov     ecx, esi
0x100151eb  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100151f0  test    eax, eax
0x100151f2  jnz     short loc_1001520C
0x100151f4  movzx   eax, word ptr [esi+8]
0x100151f8  push    8; Type
0x100151fa  push    eax; C
0x100151fb  call    ds:__imp__iswctype
0x10015201  add     esp, 8
0x10015204  test    eax, eax
0x10015206  jnz     loc_10015322
0x1001520c  push    9
0x1001520e  mov     edx, offset aTransform; "transform"
0x10015213  mov     ecx, esi
0x10015215  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001521a  test    eax, eax
0x1001521c  jnz     short loc_10015236
0x1001521e  movzx   eax, word ptr [esi+12h]
0x10015222  push    8; Type
0x10015224  push    eax; C
0x10015225  call    ds:__imp__iswctype
0x1001522b  add     esp, 8
0x1001522e  test    eax, eax
0x10015230  jnz     loc_10015322
0x10015236  push    5
0x10015238  mov     edx, offset aAlter; "alter"
0x1001523d  mov     ecx, esi
0x1001523f  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015244  test    eax, eax
0x10015246  jnz     short loc_10015260
0x10015248  movzx   eax, word ptr [esi+0Ah]
0x1001524c  push    8; Type
0x1001524e  push    eax; C
0x1001524f  call    ds:__imp__iswctype
0x10015255  add     esp, 8
0x10015258  test    eax, eax
0x1001525a  jnz     loc_10015322
0x10015260  push    6
0x10015262  mov     edx, offset aCreate; "create"
0x10015267  mov     ecx, esi
0x10015269  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001526e  test    eax, eax
0x10015270  jnz     short loc_1001528A
0x10015272  movzx   eax, word ptr [esi+0Ch]
0x10015276  push    8; Type
0x10015278  push    eax; C
0x10015279  call    ds:__imp__iswctype
0x1001527f  add     esp, 8
0x10015282  test    eax, eax
0x10015284  jnz     loc_10015322
0x1001528a  push    4
0x1001528c  mov     edx, offset aDrop; "drop"
0x10015291  mov     ecx, esi
0x10015293  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015298  test    eax, eax
0x1001529a  jnz     short loc_100152B0
0x1001529c  movzx   eax, word ptr [esi+8]
0x100152a0  push    8; Type
0x100152a2  push    eax; C
0x100152a3  call    ds:__imp__iswctype
0x100152a9  add     esp, 8
0x100152ac  test    eax, eax
0x100152ae  jnz     short loc_10015322
0x100152b0  push    9
0x100152b2  mov     edx, offset aProcedure; "procedure"
0x100152b7  mov     ecx, esi
0x100152b9  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100152be  test    eax, eax
0x100152c0  jnz     short loc_100152D6
0x100152c2  movzx   eax, word ptr [esi+12h]
0x100152c6  push    8; Type
0x100152c8  push    eax; C
0x100152c9  call    ds:__imp__iswctype
0x100152cf  add     esp, 8
0x100152d2  test    eax, eax
0x100152d4  jnz     short loc_10015322
0x100152d6  push    0Ah
0x100152d8  mov     edx, offset aParameters_1; "parameters"
0x100152dd  mov     ecx, esi
0x100152df  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100152e4  test    eax, eax
0x100152e6  jnz     short loc_100152FC
0x100152e8  movzx   eax, word ptr [esi+14h]
0x100152ec  push    8; Type
0x100152ee  push    eax; C
0x100152ef  call    ds:__imp__iswctype
0x100152f5  add     esp, 8
0x100152f8  test    eax, eax
0x100152fa  jnz     short loc_10015322
0x100152fc  push    3
0x100152fe  mov     edx, offset aAdd; "add"
0x10015303  mov     ecx, esi
0x10015305  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001530a  test    eax, eax
0x1001530c  jnz     short loc_1001532A
0x1001530e  movzx   eax, word ptr [esi+6]
0x10015312  push    8; Type
0x10015314  push    eax; C
0x10015315  call    ds:__imp__iswctype
0x1001531b  add     esp, 8
0x1001531e  test    eax, eax
0x10015320  jz      short loc_1001532A
0x10015322  pop     edi
0x10015323  mov     eax, 1
0x10015328  pop     esi
0x10015329  retn
0x1001532a  pop     edi
0x1001532b  xor     eax, eax
0x1001532d  pop     esi
0x1001532e  retn
```
