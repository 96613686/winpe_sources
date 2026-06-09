# CVistaInterfaceCollection::CollectMigratedInterfaces(ushort const *,ushort const *)

- ea: `0x1800362c8`
- end: `0x1800365d9`
- name: `?CollectMigratedInterfaces@CVistaInterfaceCollection@@QEAAJPEBG0@Z`
- size: `785`
- prototype: `__int64 __fastcall(CVistaInterfaceCollection *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034eb4`

## callees

- `0x1800025f0`
- `0x180002a10`
- `0x18000a9c0`
- `0x18000c230`
- `0x180012874`
- `0x18003615c`
- `0x180036188`
- `0x1800362c8`
- `0x180036dfc`
- `0x180037e9c`
- `0x18003d598`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036371`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036371`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x1800363e6`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x1800363e6`

## pseudocode

```c
__int64 __fastcall CVistaInterfaceCollection::CollectMigratedInterfaces(
        CVistaInterfaceCollection *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int v5; // ebx
  LSTATUS v6; // edi
  DWORD v7; // esi
  DWORD i; // edx
  LSTATUS v9; // edi
  CVistaInterfaceSettings *v10; // rax
  CVistaInterfaceSettings *v11; // rdi
  int inited; // eax
  unsigned int v13; // edx
  DWORD pcchName; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-C0h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids);
  }
  hkey = 0;
  Uuid = 0;
  if ( a3 )
  {
    v5 = 0;
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\dot3svc\\MigrationData\\dot3svc\\Interfaces",
           0,
           0x20019u,
           &hkey);
    if ( !v6 )
      goto LABEL_16;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 19, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids, (unsigned int)v6);
    }
    v5 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
    if ( v5 >= 0 )
    {
LABEL_16:
      v7 = 0;
      for ( i = 0; ; i = v7 )
      {
        pcchName = 260;
        v9 = SHEnumKeyExW(hkey, i, pszName, &pcchName);
        if ( v9 )
          break;
        v10 = (CVistaInterfaceSettings *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&v17.Data1 = v10;
        v11 = v10;
        if ( v10 )
        {
          *(_QWORD *)v10 = 0;
          *((_QWORD *)v10 + 1) = 0;
          *((_QWORD *)v10 + 2) = 0;
          *((_DWORD *)v10 + 6) = 0;
          if ( StringToGuid(pszName, &Uuid) )
          {
            v17 = Uuid;
            inited = CVistaInterfaceSettings::InitInterface(v11, hkey, pszName, &v17, a3);
            if ( inited < 0 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  21,
                  (unsigned int)WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids,
                  (unsigned int)pszName,
                  inited);
              }
              v5 = 0;
            }
            else
            {
              v5 = CVistaInterfaceCollection::AddInterface(this, v11);
              if ( v5 < 0 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control[1].Blink)
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    20,
                    WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids,
                    (unsigned int)v5);
                }
                CVistaInterfaceSettings::`scalar deleting destructor'(v11, v13);
                goto LABEL_41;
              }
            }
          }
        }
        ++v7;
      }
      if ( v9 != 259 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 22, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids, (unsigned int)v9);
        }
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        else
          v5 = v9;
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_41:
  SafeCloseKey(&hkey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 23, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800362c8  mov     [rsp-8+arg_8], rbx
0x1800362cd  push    rbp
0x1800362ce  push    rsi
0x1800362cf  push    rdi
0x1800362d0  push    r14
0x1800362d2  push    r15
0x1800362d4  lea     rbp, [rsp-180h]
0x1800362dc  sub     rsp, 280h
0x1800362e3  mov     rax, cs:__security_cookie
0x1800362ea  xor     rax, rsp
0x1800362ed  mov     [rbp+1A0h+var_30], rax
0x1800362f4  mov     r14, r8
0x1800362f7  mov     r15, rcx
0x1800362fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180036301  lea     rax, WPP_GLOBAL_Control
0x180036308  cmp     rcx, rax
0x18003630b  jz      short loc_18003632E
0x18003630d  cmp     byte ptr [rcx+19h], 4
0x180036311  jb      short loc_18003632E
0x180036313  test    byte ptr [rcx+1Ch], 1
0x180036317  jz      short loc_18003632E
0x180036319  mov     rcx, [rcx+10h]
0x18003631d  lea     r8, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids
0x180036324  mov     edx, 12h
0x180036329  call    WPP_SF_
0x18003632e  mov     [rsp+2A0h+hkey], 0
0x180036337  xorps   xmm0, xmm0
0x18003633a  movups  xmmword ptr [rsp+2A0h+Uuid.Data1], xmm0
0x18003633f  test    r14, r14
0x180036342  jnz     short loc_18003634E
0x180036344  mov     ebx, 80070057h
0x180036349  jmp     loc_180036570
0x18003634e  lea     rax, [rsp+2A0h+hkey]
0x180036353  mov     r9d, 20019h; samDesired
0x180036359  xor     r8d, r8d; ulOptions
0x18003635c  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180036361  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\dot3svc\\Migration"...
0x180036368  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003636f  xor     ebx, ebx
0x180036371  call    cs:__imp_RegOpenKeyExW
0x180036377  mov     edi, eax
0x180036379  test    eax, eax
0x18003637b  jz      short loc_1800363CB
0x18003637d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036384  lea     rax, WPP_GLOBAL_Control
0x18003638b  cmp     rcx, rax
0x18003638e  jz      short loc_1800363B2
0x180036390  cmp     byte ptr [rcx+19h], 1
0x180036394  jb      short loc_1800363B2
0x180036396  test    byte ptr [rcx+1Ch], 1
0x18003639a  jz      short loc_1800363B2
0x18003639c  mov     rcx, [rcx+10h]
0x1800363a0  lea     edx, [rbx+13h]
0x1800363a3  mov     r9d, edi
0x1800363a6  lea     r8, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids
0x1800363ad  call    WPP_SF_d
0x1800363b2  test    edi, edi
0x1800363b4  jg      short loc_1800363BA
0x1800363b6  mov     ebx, edi
0x1800363b8  jmp     short loc_1800363C3
0x1800363ba  movzx   ebx, di
0x1800363bd  or      ebx, 80070000h
0x1800363c3  test    ebx, ebx
0x1800363c5  js      loc_180036570
0x1800363cb  xor     esi, esi
0x1800363cd  xor     edx, edx; dwIndex
0x1800363cf  mov     rcx, [rsp+2A0h+hkey]; hkey
0x1800363d4  lea     r9, [rsp+2A0h+pcchName]; pcchName
0x1800363d9  lea     r8, [rsp+2A0h+pszName]; pszName
0x1800363de  mov     [rsp+2A0h+pcchName], 104h
0x1800363e6  call    cs:__imp_SHEnumKeyExW
0x1800363ec  mov     edi, eax
0x1800363ee  test    eax, eax
0x1800363f0  jnz     loc_180036520
0x1800363f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800363fd  lea     ecx, [rax+30h]; unsigned __int64
0x180036400  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036405  mov     qword ptr [rsp+2A0h+var_260.Data1], rax
0x18003640a  mov     rdi, rax
0x18003640d  test    rax, rax
0x180036410  jz      loc_180036517
0x180036416  mov     qword ptr [rax], 0
0x18003641d  mov     qword ptr [rax+8], 0
0x180036425  mov     qword ptr [rax+10h], 0
0x18003642d  mov     dword ptr [rax+18h], 0
0x180036434  test    rax, rax
0x180036437  jz      loc_180036517
0x18003643d  lea     rdx, [rsp+2A0h+Uuid]; Uuid
0x180036442  lea     rcx, [rsp+2A0h+pszName]; StringUuid
0x180036447  call    ?StringToGuid@@YA_NPEAGAEAU_GUID@@@Z; StringToGuid(ushort *,_GUID &)
0x18003644c  test    al, al
0x18003644e  jz      loc_180036517
0x180036454  movaps  xmm0, xmmword ptr [rsp+2A0h+Uuid.Data1]
0x180036459  lea     r9, [rsp+2A0h+var_260]; struct _GUID
0x18003645e  mov     rdx, [rsp+2A0h+hkey]; hKey
0x180036463  lea     r8, [rsp+2A0h+pszName]; lpSubKey
0x180036468  mov     rcx, rdi; this
0x18003646b  movdqa  xmmword ptr [rsp+2A0h+var_260.Data1], xmm0
0x180036471  mov     [rsp+2A0h+phkResult], r14; unsigned __int16 *
0x180036476  call    ?InitInterface@CVistaInterfaceSettings@@QEAAJPEAUHKEY__@@PEBGU_GUID@@1@Z; CVistaInterfaceSettings::InitInterface(HKEY__ *,ushort const *,_GUID,ushort const *)
0x18003647b  test    eax, eax
0x18003647d  js      short loc_1800364D8
0x18003647f  mov     rdx, rdi; struct CVistaInterfaceSettings *
0x180036482  mov     rcx, r15; this
0x180036485  call    ?AddInterface@CVistaInterfaceCollection@@QEAAJPEAVCVistaInterfaceSettings@@@Z; CVistaInterfaceCollection::AddInterface(CVistaInterfaceSettings *)
0x18003648a  mov     ebx, eax
0x18003648c  test    eax, eax
0x18003648e  jns     loc_180036517
0x180036494  mov     rcx, cs:WPP_GLOBAL_Control
0x18003649b  lea     rax, WPP_GLOBAL_Control
0x1800364a2  cmp     rcx, rax
0x1800364a5  jz      short loc_1800364CB
0x1800364a7  cmp     byte ptr [rcx+19h], 1
0x1800364ab  jb      short loc_1800364CB
0x1800364ad  test    byte ptr [rcx+1Ch], 1
0x1800364b1  jz      short loc_1800364CB
0x1800364b3  mov     rcx, [rcx+10h]
0x1800364b7  lea     r8, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids
0x1800364be  mov     edx, 14h
0x1800364c3  mov     r9d, ebx
0x1800364c6  call    WPP_SF_d
0x1800364cb  mov     rcx, rdi; this
0x1800364ce  call    ??_GCVistaInterfaceSettings@@QEAAPEAXI@Z; CVistaInterfaceSettings::`scalar deleting destructor'(uint)
0x1800364d3  jmp     loc_180036570
0x1800364d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364df  lea     rdx, WPP_GLOBAL_Control
0x1800364e6  cmp     rcx, rdx
0x1800364e9  jz      short loc_180036515
0x1800364eb  cmp     byte ptr [rcx+19h], 1
0x1800364ef  jb      short loc_180036515
0x1800364f1  test    byte ptr [rcx+1Ch], 1
0x1800364f5  jz      short loc_180036515
0x1800364f7  mov     rcx, [rcx+10h]
0x1800364fb  lea     r9, [rsp+2A0h+pszName]
0x180036500  mov     edx, 15h
0x180036505  mov     dword ptr [rsp+2A0h+phkResult], eax
0x180036509  lea     r8, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids
0x180036510  call    WPP_SF_Sd
0x180036515  xor     ebx, ebx
0x180036517  inc     esi
0x180036519  mov     edx, esi
0x18003651b  jmp     loc_1800363CF
0x180036520  cmp     edi, 103h
0x180036526  jz      short loc_180036570
0x180036528  mov     rcx, cs:WPP_GLOBAL_Control
0x18003652f  lea     rax, WPP_GLOBAL_Control
0x180036536  cmp     rcx, rax
0x180036539  jz      short loc_18003655F
0x18003653b  cmp     byte ptr [rcx+19h], 1
0x18003653f  jb      short loc_18003655F
0x180036541  test    byte ptr [rcx+1Ch], 1
0x180036545  jz      short loc_18003655F
0x180036547  mov     rcx, [rcx+10h]
0x18003654b  lea     r8, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids
0x180036552  mov     edx, 16h
0x180036557  mov     r9d, edi
0x18003655a  call    WPP_SF_d
0x18003655f  test    edi, edi
0x180036561  jg      short loc_180036567
0x180036563  mov     ebx, edi
0x180036565  jmp     short loc_180036570
0x180036567  movzx   ebx, di
0x18003656a  or      ebx, 80070000h
0x180036570  lea     rcx, [rsp+2A0h+hkey]; HKEY *
0x180036575  call    ?SafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * &)
0x18003657a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036581  lea     rax, WPP_GLOBAL_Control
0x180036588  cmp     rcx, rax
0x18003658b  jz      short loc_1800365B1
0x18003658d  cmp     byte ptr [rcx+19h], 4
0x180036591  jb      short loc_1800365B1
0x180036593  test    byte ptr [rcx+1Ch], 1
0x180036597  jz      short loc_1800365B1
0x180036599  mov     rcx, [rcx+10h]
0x18003659d  lea     r8, WPP_78f4162b13ae3e9067a9e98dc19bb371_Traceguids
0x1800365a4  mov     edx, 17h
0x1800365a9  mov     r9d, ebx
0x1800365ac  call    WPP_SF_d
0x1800365b1  mov     eax, ebx
0x1800365b3  mov     rcx, [rbp+1A0h+var_30]
0x1800365ba  xor     rcx, rsp; StackCookie
0x1800365bd  call    __security_check_cookie
0x1800365c2  mov     rbx, [rsp+2A0h+arg_8]
0x1800365ca  add     rsp, 280h
0x1800365d1  pop     r15
0x1800365d3  pop     r14
0x1800365d5  pop     rdi
0x1800365d6  pop     rsi
0x1800365d7  pop     rbp
0x1800365d8  retn
```
