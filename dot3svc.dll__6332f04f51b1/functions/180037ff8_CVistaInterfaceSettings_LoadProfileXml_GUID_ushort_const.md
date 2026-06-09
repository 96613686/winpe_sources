# CVistaInterfaceSettings::LoadProfileXml(_GUID,ushort const *)

- ea: `0x180037ff8`
- end: `0x1800381aa`
- name: `?LoadProfileXml@CVistaInterfaceSettings@@QEAAJU_GUID@@PEBG@Z`
- size: `434`
- prototype: `__int64 __fastcall(struct _GUID *this, struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800381b0`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x180032e4c`
- `0x1800331c4`
- `0x180037a90`
- `0x180037ff8`
- `0x18003d1b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180038082`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180038082`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAddExtensionW` at `0x1800380de`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAddExtensionW` at `0x1800380de`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAppendW` at `0x1800380b7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAppendW` at `0x1800380c9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAppendW` at `0x1800380b7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAppendW` at `0x1800380c9`

## pseudocode

```c
__int64 __fastcall CVistaInterfaceSettings::LoadProfileXml(
        struct _GUID *this,
        struct _GUID *a2,
        const unsigned __int16 *a3)
{
  struct _LIST_ENTRY *v6; // rcx
  unsigned __int64 v7; // r8
  signed int v8; // ebx
  unsigned __int64 v9; // r8
  int Profile; // eax
  int v12; // [rsp+20h] [rbp-E0h]
  WCHAR pszMore[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v14[56]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPath[264]; // [rsp+130h] [rbp+30h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 20, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    _o_wcscpy_s(pszPath, 260, a3);
    v8 = GuidToString(this + 2, pszMore, v7);
    if ( v8 >= 0 )
    {
      v8 = GuidToString(a2, v14, v9);
      if ( v8 >= 0 )
      {
        if ( PathAppendW(pszPath, pszMore) && PathAppendW(pszPath, v14) && PathAddExtensionW(pszPath, L".xml") )
        {
          Profile = LpLoadProfile(pszPath, v12);
          v8 = Profile;
          if ( Profile > 0 )
            v8 = (unsigned __int16)Profile | 0x80070000;
          if ( v8 >= 0 )
            v8 = -2147467261;
        }
        else
        {
          v8 = -2147024774;
        }
      }
    }
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v6[1].Blink) >= 4u && (BYTE4(v6[1].Blink) & 1) != 0 )
    WPP_SF_d(v6[1].Flink, 21, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180037ff8  push    rbp
0x180037ffa  push    rbx
0x180037ffb  push    rsi
0x180037ffc  push    r14
0x180037ffe  push    r15
0x180038000  lea     rbp, [rsp-250h]
0x180038008  sub     rsp, 350h
0x18003800f  mov     rax, cs:__security_cookie
0x180038016  xor     rax, rsp
0x180038019  mov     [rbp+270h+var_30], rax
0x180038020  mov     rbx, r8
0x180038023  mov     rsi, rdx
0x180038026  mov     r14, rcx
0x180038029  mov     rcx, cs:WPP_GLOBAL_Control
0x180038030  lea     r15, WPP_GLOBAL_Control
0x180038037  cmp     rcx, r15
0x18003803a  jz      short loc_180038064
0x18003803c  cmp     byte ptr [rcx+19h], 4
0x180038040  jb      short loc_180038064
0x180038042  test    byte ptr [rcx+1Ch], 1
0x180038046  jz      short loc_180038064
0x180038048  mov     rcx, [rcx+10h]
0x18003804c  lea     r8, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids
0x180038053  mov     edx, 14h
0x180038058  call    WPP_SF_
0x18003805d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038064  mov     [rsp+370h+lpMem], 0
0x18003806d  test    rbx, rbx
0x180038070  jz      loc_18003815C
0x180038076  mov     r8, rbx
0x180038079  lea     rcx, [rbp+270h+pszPath]
0x18003807d  mov     edx, 104h
0x180038082  call    cs:__imp__o_wcscpy_s
0x180038088  lea     rcx, [r14+20h]; struct _GUID *
0x18003808c  lea     rdx, [rsp+370h+pszMore]; unsigned __int16 *
0x180038091  call    ?GuidToString@@YAJAEAU_GUID@@PEAG_K@Z; GuidToString(_GUID &,ushort *,unsigned __int64)
0x180038096  mov     ebx, eax
0x180038098  test    eax, eax
0x18003809a  js      short loc_1800380ED
0x18003809c  lea     rdx, [rbp+270h+var_2B0]; unsigned __int16 *
0x1800380a0  mov     rcx, rsi; struct _GUID *
0x1800380a3  call    ?GuidToString@@YAJAEAU_GUID@@PEAG_K@Z; GuidToString(_GUID &,ushort *,unsigned __int64)
0x1800380a8  mov     ebx, eax
0x1800380aa  test    eax, eax
0x1800380ac  js      short loc_1800380ED
0x1800380ae  lea     rdx, [rsp+370h+pszMore]; pszMore
0x1800380b3  lea     rcx, [rbp+270h+pszPath]; pszPath
0x1800380b7  call    cs:__imp_PathAppendW
0x1800380bd  test    eax, eax
0x1800380bf  jz      short loc_1800380E8
0x1800380c1  lea     rdx, [rbp+270h+var_2B0]; pszMore
0x1800380c5  lea     rcx, [rbp+270h+pszPath]; pszPath
0x1800380c9  call    cs:__imp_PathAppendW
0x1800380cf  test    eax, eax
0x1800380d1  jz      short loc_1800380E8
0x1800380d3  lea     rdx, pszExt; ".xml"
0x1800380da  lea     rcx, [rbp+270h+pszPath]; pszPath
0x1800380de  call    cs:__imp_PathAddExtensionW
0x1800380e4  test    eax, eax
0x1800380e6  jnz     short loc_1800380F6
0x1800380e8  mov     ebx, 8007007Ah
0x1800380ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380f4  jmp     short loc_180038161
0x1800380f6  lea     r9, [rsp+370h+lpMem]
0x1800380fb  xor     r8d, r8d
0x1800380fe  xor     edx, edx
0x180038100  lea     rcx, [rbp+270h+pszPath]; unsigned __int16 *
0x180038104  call    LpLoadProfile
0x180038109  mov     ebx, eax
0x18003810b  test    eax, eax
0x18003810d  jle     short loc_180038118
0x18003810f  movzx   ebx, ax
0x180038112  or      ebx, 80070000h
0x180038118  test    ebx, ebx
0x18003811a  js      short loc_180038148
0x18003811c  cmp     [rsp+370h+lpMem], 0
0x180038122  jz      short loc_180038143
0x180038124  movaps  xmm0, xmmword ptr [rsi]
0x180038127  lea     rdx, [rsp+370h+var_330]; struct _GUID
0x18003812c  mov     r8, [rsp+370h+lpMem]; unsigned __int16 *
0x180038131  mov     rcx, r14; this
0x180038134  movdqa  xmmword ptr [rsp+370h+var_330.Data1], xmm0
0x18003813a  call    ?AddProfile@CVistaInterfaceSettings@@QEAAJU_GUID@@PEBG@Z; CVistaInterfaceSettings::AddProfile(_GUID,ushort const *)
0x18003813f  mov     ebx, eax
0x180038141  jmp     short loc_180038148
0x180038143  mov     ebx, 80004003h
0x180038148  cmp     [rsp+370h+lpMem], 0
0x18003814e  jz      short loc_1800380ED
0x180038150  mov     rcx, [rsp+370h+lpMem]; lpMem
0x180038155  call    LpFreeProfileXml
0x18003815a  jmp     short loc_1800380ED
0x18003815c  mov     ebx, 80070057h
0x180038161  cmp     rcx, r15
0x180038164  jz      short loc_18003818A
0x180038166  cmp     byte ptr [rcx+19h], 4
0x18003816a  jb      short loc_18003818A
0x18003816c  test    byte ptr [rcx+1Ch], 1
0x180038170  jz      short loc_18003818A
0x180038172  mov     rcx, [rcx+10h]
0x180038176  lea     r8, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids
0x18003817d  mov     edx, 15h
0x180038182  mov     r9d, ebx
0x180038185  call    WPP_SF_d
0x18003818a  mov     eax, ebx
0x18003818c  mov     rcx, [rbp+270h+var_30]
0x180038193  xor     rcx, rsp; StackCookie
0x180038196  call    __security_check_cookie
0x18003819b  add     rsp, 350h
0x1800381a2  pop     r15
0x1800381a4  pop     r14
0x1800381a6  pop     rsi
0x1800381a7  pop     rbx
0x1800381a8  pop     rbp
0x1800381a9  retn
```
