# LsaDbLogInfoTrustedDomainList(void)

- ea: `0x18000988c`
- end: `0x1800099ab`
- name: `?LsaDbLogInfoTrustedDomainList@@YAXXZ`
- size: `287`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180009b24`
- `0x18000af18`
- `0x18000bae8`

## callees

- `0x18000988c`
- `0x18000fd18`
- `0x18000fe50`
- `0x18000fee8`

## import_xrefs

- `LSASRV!LsapDbExpIsCacheBuilding` at `0x1800098dd`
- `LSASRV!LsapDbExpIsCacheBuilding` at `0x1800098dd`
- `LSASRV!LsapDbExpIsCacheValid` at `0x1800098e8`
- `LSASRV!LsapDbExpIsCacheValid` at `0x1800098e8`

## pseudocode

```c
void LsaDbLogInfoTrustedDomainList(void)
{
  int v0; // edx
  int v1; // r8d
  _QWORD *v2; // rcx
  int IsCacheBuilding; // ebx
  unsigned __int8 IsCacheValid; // al
  HLOCAL *v5; // rbx
  int v6; // edi

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    v2 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      IsCacheBuilding = (unsigned __int8)LsapDbExpIsCacheBuilding(2);
      IsCacheValid = LsapDbExpIsCacheValid(2);
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
        IsCacheValid,
        IsCacheBuilding);
      v2 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
          LsaDbpTrustedDomainList,
          *(&LsaDbpTrustedDomainList + 1));
        v2 = WPP_GLOBAL_Control;
      }
    }
    v5 = (HLOCAL *)hMem;
    v6 = 1;
    while ( v5 != &hMem )
    {
      if ( (*((_DWORD *)v2 + 7) & 0x100) != 0 )
      {
        WPP_SF_dZ(v2[2], v0, v1, v6, (__int64)(v5 + 2));
        v2 = WPP_GLOBAL_Control;
      }
      v5 = (HLOCAL *)*v5;
      ++v6;
    }
    if ( (*((_DWORD *)v2 + 7) & 0x100) != 0 )
      WPP_SF_(v2[2], 30, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
  }
}

```

## disassembly

```asm
0x18000988c  push    rbx
0x18000988e  push    rsi
0x18000988f  push    rdi
0x180009890  push    r14
0x180009892  sub     rsp, 38h
0x180009896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000989d  mov     esi, 100h
0x1800098a2  test    [rcx+1Ch], esi
0x1800098a5  jz      loc_1800099A1
0x1800098ab  cmp     byte ptr [rcx+19h], 4
0x1800098af  jb      loc_1800099A1
0x1800098b5  mov     rcx, [rcx+10h]
0x1800098b9  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x1800098c0  mov     edx, 1Ah
0x1800098c5  call    WPP_SF_
0x1800098ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098d1  test    [rcx+1Ch], esi
0x1800098d4  jz      short loc_180009947
0x1800098d6  mov     edi, 2
0x1800098db  mov     ecx, edi
0x1800098dd  call    cs:__imp_LsapDbExpIsCacheBuilding
0x1800098e3  mov     ecx, edi
0x1800098e5  movzx   ebx, al
0x1800098e8  call    cs:__imp_LsapDbExpIsCacheValid
0x1800098ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098f5  lea     edx, [rdi+19h]
0x1800098f8  movzx   r9d, al
0x1800098fc  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009903  mov     dword ptr [rsp+58h+var_38], ebx
0x180009907  mov     rcx, [rcx+10h]
0x18000990b  call    WPP_SF_dd
0x180009910  mov     rcx, cs:WPP_GLOBAL_Control
0x180009917  test    [rcx+1Ch], esi
0x18000991a  jz      short loc_180009947
0x18000991c  mov     eax, dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A+4; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x180009922  lea     edx, [rdi+1Ah]
0x180009925  mov     r9d, dword ptr cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x18000992c  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009933  mov     rcx, [rcx+10h]
0x180009937  mov     dword ptr [rsp+58h+var_38], eax
0x18000993b  call    WPP_SF_dd
0x180009940  mov     rcx, cs:WPP_GLOBAL_Control
0x180009947  mov     rbx, cs:hMem
0x18000994e  lea     r14, hMem
0x180009955  mov     edi, 1
0x18000995a  jmp     short loc_180009982
0x18000995c  test    [rcx+1Ch], esi
0x18000995f  jz      short loc_18000997D
0x180009961  mov     rcx, [rcx+10h]
0x180009965  lea     rax, [rbx+10h]
0x180009969  mov     r9d, edi
0x18000996c  mov     [rsp+58h+var_38], rax
0x180009971  call    WPP_SF_dZ
0x180009976  mov     rcx, cs:WPP_GLOBAL_Control
0x18000997d  mov     rbx, [rbx]
0x180009980  inc     edi
0x180009982  cmp     rbx, r14
0x180009985  jnz     short loc_18000995C
0x180009987  test    [rcx+1Ch], esi
0x18000998a  jz      short loc_1800099A1
0x18000998c  mov     rcx, [rcx+10h]
0x180009990  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009997  mov     edx, 1Eh
0x18000999c  call    WPP_SF_
0x1800099a1  add     rsp, 38h
0x1800099a5  pop     r14
0x1800099a7  pop     rdi
0x1800099a8  pop     rsi
0x1800099a9  pop     rbx
0x1800099aa  retn
```
