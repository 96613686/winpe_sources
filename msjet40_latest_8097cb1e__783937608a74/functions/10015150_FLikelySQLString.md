# FLikelySQLString

- ea: `0x10015150`
- end: `0x1001546f`
- name: `FLikelySQLString`
- size: `799`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10015480`
- `0x100155a0`

## callees

- `0x10012af0`
- `0x10015150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015163`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015197`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151c1`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151eb`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015215`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001523f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015269`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015293`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152bd`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152e7`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015311`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001533b`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015365`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001538f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100153b9`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100153e3`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015409`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001542f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015455`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015163`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015197`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151c1`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100151eb`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015215`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001523f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015269`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015293`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152bd`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100152e7`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015311`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001533b`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015365`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001538f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100153b9`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100153e3`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015409`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001542f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10015455`

## string_xrefs

- `0x100152a6`: `update`
- `0x100151fe`: `commit`
- `0x1001527c`: `delete`
- `0x100153a2`: `create`
- `0x10015228`: `rollback`

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
0x10015150  mov     edi, edi
0x10015152  push    esi
0x10015153  mov     esi, ecx
0x10015155  push    edi
0x10015156  movzx   eax, word ptr [esi]
0x10015159  test    ax, ax
0x1001515c  jz      short loc_1001517E
0x1001515e  mov     ecx, eax
0x10015160  push    8; Type
0x10015162  push    ecx; C
0x10015163  call    ds:__imp__iswctype
0x10015169  add     esp, 8
0x1001516c  test    eax, eax
0x1001516e  jz      short loc_1001517E
0x10015170  movzx   eax, word ptr [esi+2]
0x10015174  add     esi, 2
0x10015177  mov     ecx, eax
0x10015179  test    ax, ax
0x1001517c  jnz     short loc_10015160
0x1001517e  push    5
0x10015180  mov     edx, offset aGrant; "grant"
0x10015185  mov     ecx, esi
0x10015187  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001518c  test    eax, eax
0x1001518e  jnz     short loc_100151A8
0x10015190  movzx   eax, word ptr [esi+0Ah]
0x10015194  push    8; Type
0x10015196  push    eax; C
0x10015197  call    ds:__imp__iswctype
0x1001519d  add     esp, 8
0x100151a0  test    eax, eax
0x100151a2  jnz     loc_10015462
0x100151a8  push    6
0x100151aa  mov     edx, offset aRevoke; "revoke"
0x100151af  mov     ecx, esi
0x100151b1  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100151b6  test    eax, eax
0x100151b8  jnz     short loc_100151D2
0x100151ba  movzx   eax, word ptr [esi+0Ch]
0x100151be  push    8; Type
0x100151c0  push    eax; C
0x100151c1  call    ds:__imp__iswctype
0x100151c7  add     esp, 8
0x100151ca  test    eax, eax
0x100151cc  jnz     loc_10015462
0x100151d2  push    5
0x100151d4  mov     edx, offset aBegin; "begin"
0x100151d9  mov     ecx, esi
0x100151db  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100151e0  test    eax, eax
0x100151e2  jnz     short loc_100151FC
0x100151e4  movzx   eax, word ptr [esi+0Ah]
0x100151e8  push    8; Type
0x100151ea  push    eax; C
0x100151eb  call    ds:__imp__iswctype
0x100151f1  add     esp, 8
0x100151f4  test    eax, eax
0x100151f6  jnz     loc_10015462
0x100151fc  push    6
0x100151fe  mov     edx, offset aCommit; "commit"
0x10015203  mov     ecx, esi
0x10015205  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001520a  test    eax, eax
0x1001520c  jnz     short loc_10015226
0x1001520e  movzx   eax, word ptr [esi+0Ch]
0x10015212  push    8; Type
0x10015214  push    eax; C
0x10015215  call    ds:__imp__iswctype
0x1001521b  add     esp, 8
0x1001521e  test    eax, eax
0x10015220  jnz     loc_10015462
0x10015226  push    8
0x10015228  mov     edx, offset aRollback; "rollback"
0x1001522d  mov     ecx, esi
0x1001522f  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015234  test    eax, eax
0x10015236  jnz     short loc_10015250
0x10015238  movzx   eax, word ptr [esi+10h]
0x1001523c  push    8; Type
0x1001523e  push    eax; C
0x1001523f  call    ds:__imp__iswctype
0x10015245  add     esp, 8
0x10015248  test    eax, eax
0x1001524a  jnz     loc_10015462
0x10015250  push    6
0x10015252  mov     edx, offset aSelect_0; "select"
0x10015257  mov     ecx, esi
0x10015259  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001525e  test    eax, eax
0x10015260  jnz     short loc_1001527A
0x10015262  movzx   eax, word ptr [esi+0Ch]
0x10015266  push    8; Type
0x10015268  push    eax; C
0x10015269  call    ds:__imp__iswctype
0x1001526f  add     esp, 8
0x10015272  test    eax, eax
0x10015274  jnz     loc_10015462
0x1001527a  push    6
0x1001527c  mov     edx, offset aDelete; "delete"
0x10015281  mov     ecx, esi
0x10015283  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015288  test    eax, eax
0x1001528a  jnz     short loc_100152A4
0x1001528c  movzx   eax, word ptr [esi+0Ch]
0x10015290  push    8; Type
0x10015292  push    eax; C
0x10015293  call    ds:__imp__iswctype
0x10015299  add     esp, 8
0x1001529c  test    eax, eax
0x1001529e  jnz     loc_10015462
0x100152a4  push    6
0x100152a6  mov     edx, offset aUpdate; "update"
0x100152ab  mov     ecx, esi
0x100152ad  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100152b2  test    eax, eax
0x100152b4  jnz     short loc_100152CE
0x100152b6  movzx   eax, word ptr [esi+0Ch]
0x100152ba  push    8; Type
0x100152bc  push    eax; C
0x100152bd  call    ds:__imp__iswctype
0x100152c3  add     esp, 8
0x100152c6  test    eax, eax
0x100152c8  jnz     loc_10015462
0x100152ce  push    6
0x100152d0  mov     edx, offset aInsert; "insert"
0x100152d5  mov     ecx, esi
0x100152d7  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100152dc  test    eax, eax
0x100152de  jnz     short loc_100152F8
0x100152e0  movzx   eax, word ptr [esi+0Ch]
0x100152e4  push    8; Type
0x100152e6  push    eax; C
0x100152e7  call    ds:__imp__iswctype
0x100152ed  add     esp, 8
0x100152f0  test    eax, eax
0x100152f2  jnz     loc_10015462
0x100152f8  push    7
0x100152fa  mov     edx, offset aExecute; "execute"
0x100152ff  mov     ecx, esi
0x10015301  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015306  test    eax, eax
0x10015308  jnz     short loc_10015322
0x1001530a  movzx   eax, word ptr [esi+0Eh]
0x1001530e  push    8; Type
0x10015310  push    eax; C
0x10015311  call    ds:__imp__iswctype
0x10015317  add     esp, 8
0x1001531a  test    eax, eax
0x1001531c  jnz     loc_10015462
0x10015322  push    4
0x10015324  mov     edx, offset aExec_0; "exec"
0x10015329  mov     ecx, esi
0x1001532b  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015330  test    eax, eax
0x10015332  jnz     short loc_1001534C
0x10015334  movzx   eax, word ptr [esi+8]
0x10015338  push    8; Type
0x1001533a  push    eax; C
0x1001533b  call    ds:__imp__iswctype
0x10015341  add     esp, 8
0x10015344  test    eax, eax
0x10015346  jnz     loc_10015462
0x1001534c  push    9
0x1001534e  mov     edx, offset aTransform; "transform"
0x10015353  mov     ecx, esi
0x10015355  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001535a  test    eax, eax
0x1001535c  jnz     short loc_10015376
0x1001535e  movzx   eax, word ptr [esi+12h]
0x10015362  push    8; Type
0x10015364  push    eax; C
0x10015365  call    ds:__imp__iswctype
0x1001536b  add     esp, 8
0x1001536e  test    eax, eax
0x10015370  jnz     loc_10015462
0x10015376  push    5
0x10015378  mov     edx, offset aAlter; "alter"
0x1001537d  mov     ecx, esi
0x1001537f  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015384  test    eax, eax
0x10015386  jnz     short loc_100153A0
0x10015388  movzx   eax, word ptr [esi+0Ah]
0x1001538c  push    8; Type
0x1001538e  push    eax; C
0x1001538f  call    ds:__imp__iswctype
0x10015395  add     esp, 8
0x10015398  test    eax, eax
0x1001539a  jnz     loc_10015462
0x100153a0  push    6
0x100153a2  mov     edx, offset aCreate; "create"
0x100153a7  mov     ecx, esi
0x100153a9  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100153ae  test    eax, eax
0x100153b0  jnz     short loc_100153CA
0x100153b2  movzx   eax, word ptr [esi+0Ch]
0x100153b6  push    8; Type
0x100153b8  push    eax; C
0x100153b9  call    ds:__imp__iswctype
0x100153bf  add     esp, 8
0x100153c2  test    eax, eax
0x100153c4  jnz     loc_10015462
0x100153ca  push    4
0x100153cc  mov     edx, offset aDrop; "drop"
0x100153d1  mov     ecx, esi
0x100153d3  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100153d8  test    eax, eax
0x100153da  jnz     short loc_100153F0
0x100153dc  movzx   eax, word ptr [esi+8]
0x100153e0  push    8; Type
0x100153e2  push    eax; C
0x100153e3  call    ds:__imp__iswctype
0x100153e9  add     esp, 8
0x100153ec  test    eax, eax
0x100153ee  jnz     short loc_10015462
0x100153f0  push    9
0x100153f2  mov     edx, offset aProcedure; "procedure"
0x100153f7  mov     ecx, esi
0x100153f9  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100153fe  test    eax, eax
0x10015400  jnz     short loc_10015416
0x10015402  movzx   eax, word ptr [esi+12h]
0x10015406  push    8; Type
0x10015408  push    eax; C
0x10015409  call    ds:__imp__iswctype
0x1001540f  add     esp, 8
0x10015412  test    eax, eax
0x10015414  jnz     short loc_10015462
0x10015416  push    0Ah
0x10015418  mov     edx, offset aParameters_1; "parameters"
0x1001541d  mov     ecx, esi
0x1001541f  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015424  test    eax, eax
0x10015426  jnz     short loc_1001543C
0x10015428  movzx   eax, word ptr [esi+14h]
0x1001542c  push    8; Type
0x1001542e  push    eax; C
0x1001542f  call    ds:__imp__iswctype
0x10015435  add     esp, 8
0x10015438  test    eax, eax
0x1001543a  jnz     short loc_10015462
0x1001543c  push    3
0x1001543e  mov     edx, offset aAdd; "add"
0x10015443  mov     ecx, esi
0x10015445  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1001544a  test    eax, eax
0x1001544c  jnz     short loc_1001546A
0x1001544e  movzx   eax, word ptr [esi+6]
0x10015452  push    8; Type
0x10015454  push    eax; C
0x10015455  call    ds:__imp__iswctype
0x1001545b  add     esp, 8
0x1001545e  test    eax, eax
0x10015460  jz      short loc_1001546A
0x10015462  pop     edi
0x10015463  mov     eax, 1
0x10015468  pop     esi
0x10015469  retn
0x1001546a  pop     edi
0x1001546b  xor     eax, eax
0x1001546d  pop     esi
0x1001546e  retn
```
