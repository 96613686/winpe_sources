# areg_ReadEntryFromRegistry

- ea: `0x1800264e4`
- end: `0x1800269c4`
- name: `areg_ReadEntryFromRegistry`
- size: `1248`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `6`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800259f0`
- `0x180025d1c`
- `0x180025fb4`
- `0x180026314`
- `0x180037cfc`
- `0x18004abac`

## callees

- `0x18000b130`
- `0x1800264e4`
- `0x1800324e4`
- `0x1800370f8`
- `0x180046ec0`
- `0x18004a860`
- `0x18004af6c`
- `0x1800623a4`
- `0x180085fb8`
- `0x180086384`
- `0x180086c38`
- `0x180088578`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026913`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800265a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800265a0`

## string_xrefs

- `0x18002695a`: `Leaving areg_ReadEntryFromRegistry:`
- `0x180026969`: `Leave areg_ReadEntryFromRegistry():`

## pseudocode

```c
_DWORD *__fastcall areg_ReadEntryFromRegistry(WCHAR *Src, int a2, int a3)
{
  _DWORD *v3; // rbx
  LSTATUS v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // r13d
  unsigned int v17; // r12d
  int v18; // esi
  int v19; // edi
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  void *v36; // [rsp+28h] [rbp-E8h]
  void *v37; // [rsp+28h] [rbp-E8h]
  void *v38; // [rsp+28h] [rbp-E8h]
  void *v39; // [rsp+28h] [rbp-E8h]
  void *v40; // [rsp+28h] [rbp-E8h]
  void *v41; // [rsp+28h] [rbp-E8h]
  void *v42; // [rsp+28h] [rbp-E8h]
  void *v43; // [rsp+28h] [rbp-E8h]
  void *v44; // [rsp+28h] [rbp-E8h]
  void *v45; // [rsp+28h] [rbp-E8h]
  int v46; // [rsp+70h] [rbp-A0h]
  __int64 v47; // [rsp+A8h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-60h] BYREF
  void *v49; // [rsp+B8h] [rbp-58h] BYREF
  void *v50; // [rsp+C0h] [rbp-50h] BYREF
  void *v51; // [rsp+C8h] [rbp-48h] BYREF
  void *v52; // [rsp+D0h] [rbp-40h] BYREF
  void *v53; // [rsp+D8h] [rbp-38h] BYREF
  __int64 v54; // [rsp+E0h] [rbp-30h] BYREF
  __int64 v55; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-20h] BYREF

  v3 = 0;
  hKey = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v55 = 0;
  LODWORD(v56) = g_DefaultCompartmentId;
  v54 = 0;
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_Sdd(1047, 85, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (_DWORD)Src, a2, a3);
  v7 = RegOpenKeyExW(g_hAregRegKey, Src, 0, 0x20019u, &hKey);
  if ( v7 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 86, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (_DWORD)Src, v7);
    hKey = 0;
    goto LABEL_38;
  }
  Reg_GetValueEx2(v8, hKey, v9, 0x8Cu, 4, (__int64)v36, (__int64 *)((char *)&v54 + 4));
  if ( a3 && HIDWORD(v54) )
  {
    if ( (SBYTE2(xmmword_1800AB5A0) & 0x80u) == 0 )
      goto LABEL_36;
    v12 = 87;
    goto LABEL_11;
  }
  Reg_GetValueEx2(v10, hKey, v11, 0x82u, 4, (__int64)v37, &v54);
  if ( !a2 || (_DWORD)v54 )
  {
    if ( !(unsigned int)Reg_GetValueEx2(v13, hKey, v14, 0x8Bu, 4, (__int64)v38, &v55) )
    {
      v16 = v55 & 1;
      v17 = ((unsigned int)v55 >> 1) & 1;
      v18 = v55 & 4;
      v19 = v55 & 8;
      if ( !(unsigned int)Reg_GetValueEx2(0, hKey, v15, 0, 1, (__int64)v39, &v49)
        && !(unsigned int)Reg_GetValueEx2(v20, hKey, v21, 4u, 1, (__int64)v40, &v51)
        && !(unsigned int)Reg_GetValueEx2(v22, hKey, v23, 3u, 1, (__int64)v41, &v50)
        && !(unsigned int)Areg_ReadAddrArrayFromRegistry(hKey, L"HostAddrs")
        && !(unsigned int)Areg_ReadAddrArrayFromRegistry(hKey, L"DnsServers")
        && !(unsigned int)Reg_GetValueEx2(v24, hKey, v25, 0x7Fu, 3, (__int64)v42, &v53)
        && !(unsigned int)Reg_GetValueEx2(v26, hKey, v27, 0x7Eu, 3, (__int64)v43, &v52)
        && !(unsigned int)Reg_GetValueEx2(v28, hKey, v29, 0x89u, 4, (__int64)v44, (__int64 *)((char *)&v55 + 4))
        && !(unsigned int)Reg_GetValueEx2(v30, hKey, v31, 0x8Au, 4, (__int64)v45, &v56) )
      {
        v32 = -1;
        if ( v50 )
        {
          v33 = -1;
          do
            ++v33;
          while ( *((_WORD *)v50 + v33) );
        }
        if ( v51 )
        {
          do
            ++v32;
          while ( *((_WORD *)v51 + v32) );
        }
        if ( v18 || (v34 = 0, v19) )
          v34 = 8;
        if ( !(unsigned int)areg_AllocateEntry(
                              Src,
                              v49,
                              0,
                              0,
                              0,
                              (__int64)v52,
                              (__int64)v53,
                              v56,
                              SHIDWORD(v55),
                              v34,
                              v18 != 0 ? 8 : 0,
                              v19 != 0 ? 8 : 0,
                              v46,
                              0,
                              (__int64)&v47) )
        {
          v3 = (_DWORD *)v47;
          *(_DWORD *)(v47 + 256) = 1;
          v3[67] = v16;
          v3[66] = v17;
          v3[69] = v18 != 0;
          v3[70] = v19 != 0;
        }
      }
    }
    goto LABEL_36;
  }
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
  {
    v12 = 88;
LABEL_11:
    WPP_SF_S(1047, v12, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, Src);
  }
LABEL_36:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_38:
  MIDL_user_free(0);
  MIDL_user_free(0);
  MIDL_user_free(v49);
  MIDL_user_free(v50);
  MIDL_user_free(v51);
  MIDL_user_free(v52);
  MIDL_user_free(v53);
  areg_LogEntry("Leaving areg_ReadEntryFromRegistry:", v3);
  DnsPrint_AregEntry("Leave areg_ReadEntryFromRegistry():", v3);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_dd(1035, 89, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, HIDWORD(v54), v54);
  return v3;
}

```

## disassembly

```asm
0x1800264e4  push    rbp
0x1800264e6  push    rbx
0x1800264e7  push    rsi
0x1800264e8  push    rdi
0x1800264e9  push    r12
0x1800264eb  push    r13
0x1800264ed  push    r14
0x1800264ef  push    r15
0x1800264f1  lea     rbp, [rsp+8]
0x1800264f6  sub     rsp, 108h
0x1800264fd  mov     rax, cs:__security_cookie
0x180026504  xor     rax, rsp
0x180026507  mov     [rbp+30h+var_48], rax
0x18002650b  mov     eax, cs:g_DefaultCompartmentId
0x180026511  xor     r12d, r12d
0x180026514  mov     ebx, r12d
0x180026517  mov     [rbp+30h+hKey], r12
0x18002651b  mov     [rbp+30h+var_98], rbx
0x18002651f  mov     edi, r8d
0x180026522  mov     esi, edx
0x180026524  mov     [rbp+30h+var_88], r12
0x180026528  mov     r15, rcx
0x18002652b  mov     [rbp+30h+var_80], r12
0x18002652f  mov     [rbp+30h+var_78], r12
0x180026533  mov     r14d, r12d
0x180026536  mov     [rbp+30h+var_A0], r12
0x18002653a  mov     [rbp+30h+var_A8], r12
0x18002653e  mov     [rbp+30h+var_70], r12
0x180026542  mov     [rbp+30h+var_68], r12
0x180026546  mov     [rbp+30h+var_54], r12d
0x18002654a  mov     [rbp+30h+var_58], r12d
0x18002654e  mov     dword ptr [rbp+30h+var_50], eax
0x180026551  mov     [rbp+30h+var_60], r12d
0x180026555  mov     [rbp+30h+var_5C], r12d
0x180026559  cmp     byte ptr cs:xmmword_1800AB5A0+2, r12b
0x180026560  jge     short loc_180026584
0x180026562  mov     dword ptr [rsp+140h+var_118], r8d
0x180026567  lea     edx, [r12+55h]
0x18002656c  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180026573  mov     dword ptr [rsp+140h+phkResult], esi
0x180026577  mov     ecx, 417h
0x18002657c  mov     r9, r15
0x18002657f  call    WPP_SF_Sdd
0x180026584  mov     rcx, cs:g_hAregRegKey; hKey
0x18002658b  lea     rax, [rbp+30h+hKey]
0x18002658f  mov     r9d, 20019h; samDesired
0x180026595  mov     [rsp+140h+phkResult], rax; phkResult
0x18002659a  xor     r8d, r8d; ulOptions
0x18002659d  mov     rdx, r15; lpSubKey
0x1800265a0  call    cs:__imp_RegOpenKeyExW
0x1800265a6  test    eax, eax
0x1800265a8  jz      short loc_1800265D9
0x1800265aa  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800265b1  jz      short loc_1800265D0
0x1800265b3  mov     edx, 56h ; 'V'
0x1800265b8  mov     dword ptr [rsp+140h+phkResult], eax
0x1800265bc  mov     ecx, 40Bh
0x1800265c1  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x1800265c8  mov     r9, r15
0x1800265cb  call    WPP_SF_SD
0x1800265d0  mov     [rbp+30h+hKey], r12
0x1800265d4  jmp     loc_180026919
0x1800265d9  mov     rdx, [rbp+30h+hKey]
0x1800265dd  lea     rax, [rbp+30h+var_5C]
0x1800265e1  mov     [rsp+140h+var_110], rax
0x1800265e6  mov     r13d, 4
0x1800265ec  mov     r9d, 8Ch
0x1800265f2  mov     dword ptr [rsp+140h+phkResult], r13d
0x1800265f7  call    Reg_GetValueEx2
0x1800265fc  test    edi, edi
0x1800265fe  jz      short loc_180026630
0x180026600  cmp     [rbp+30h+var_5C], r12d
0x180026604  jz      short loc_180026630
0x180026606  cmp     byte ptr cs:xmmword_1800AB5A0+2, r12b
0x18002660d  jge     loc_18002690A
0x180026613  lea     edx, [r13+53h]
0x180026617  mov     ecx, 417h
0x18002661c  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180026623  mov     r9, r15
0x180026626  call    WPP_SF_S
0x18002662b  jmp     loc_18002690A
0x180026630  mov     rdx, [rbp+30h+hKey]
0x180026634  lea     rax, [rbp+30h+var_60]
0x180026638  mov     [rsp+140h+var_110], rax
0x18002663d  mov     r9d, 82h
0x180026643  mov     dword ptr [rsp+140h+phkResult], r13d
0x180026648  call    Reg_GetValueEx2
0x18002664d  test    esi, esi
0x18002664f  jz      short loc_18002666B
0x180026651  cmp     [rbp+30h+var_60], r12d
0x180026655  jnz     short loc_18002666B
0x180026657  cmp     byte ptr cs:xmmword_1800AB5A0+2, r12b
0x18002665e  jge     loc_18002690A
0x180026664  mov     edx, 58h ; 'X'
0x180026669  jmp     short loc_180026617
0x18002666b  mov     rdx, [rbp+30h+hKey]
0x18002666f  lea     rax, [rbp+30h+var_58]
0x180026673  mov     [rsp+140h+var_110], rax
0x180026678  mov     r9d, 8Bh
0x18002667e  mov     dword ptr [rsp+140h+phkResult], r13d
0x180026683  call    Reg_GetValueEx2
0x180026688  test    eax, eax
0x18002668a  jnz     loc_18002690A
0x180026690  mov     edi, [rbp+30h+var_58]
0x180026693  mov     rcx, rbx
0x180026696  mov     rdx, [rbp+30h+hKey]
0x18002669a  mov     eax, ecx
0x18002669c  mov     r12d, edi
0x18002669f  mov     r13d, edi
0x1800266a2  shr     r12d, 1
0x1800266a5  and     r13d, 1
0x1800266a9  and     r12d, 1
0x1800266ad  mov     esi, edi
0x1800266af  and     esi, 4
0x1800266b2  setnz   al
0x1800266b5  and     edi, 8
0x1800266b8  mov     [rbp+30h+var_B0], eax
0x1800266bb  mov     eax, ecx
0x1800266bd  setnz   al
0x1800266c0  xor     r9d, r9d
0x1800266c3  mov     [rbp+30h+var_AC], eax
0x1800266c6  lea     rax, [rbp+30h+var_88]
0x1800266ca  mov     [rsp+140h+var_110], rax
0x1800266cf  mov     dword ptr [rsp+140h+phkResult], 1
0x1800266d7  call    Reg_GetValueEx2
0x1800266dc  test    eax, eax
0x1800266de  jnz     loc_18002690A
0x1800266e4  mov     rdx, [rbp+30h+hKey]
0x1800266e8  lea     rax, [rbp+30h+var_78]
0x1800266ec  mov     [rsp+140h+var_110], rax
0x1800266f1  mov     r9d, 4
0x1800266f7  mov     dword ptr [rsp+140h+phkResult], 1
0x1800266ff  call    Reg_GetValueEx2
0x180026704  test    eax, eax
0x180026706  jnz     loc_18002690A
0x18002670c  mov     rdx, [rbp+30h+hKey]
0x180026710  lea     rax, [rbp+30h+var_80]
0x180026714  mov     [rsp+140h+var_110], rax
0x180026719  mov     r9d, 3
0x18002671f  mov     dword ptr [rsp+140h+phkResult], 1
0x180026727  call    Reg_GetValueEx2
0x18002672c  test    eax, eax
0x18002672e  jnz     loc_18002690A
0x180026734  mov     rcx, [rbp+30h+hKey]; hKey
0x180026738  lea     r8, [rbp+30h+var_A0]
0x18002673c  lea     rdx, aHostaddrs; "HostAddrs"
0x180026743  call    Areg_ReadAddrArrayFromRegistry
0x180026748  test    eax, eax
0x18002674a  jnz     loc_18002690A
0x180026750  mov     rcx, [rbp+30h+hKey]; hKey
0x180026754  lea     r8, [rbp+30h+var_A8]
0x180026758  lea     rdx, aDnsservers; "DnsServers"
0x18002675f  call    Areg_ReadAddrArrayFromRegistry
0x180026764  test    eax, eax
0x180026766  jnz     loc_180026906
0x18002676c  mov     rdx, [rbp+30h+hKey]
0x180026770  lea     rax, [rbp+30h+var_68]
0x180026774  mov     [rsp+140h+var_110], rax
0x180026779  mov     r9d, 7Fh
0x18002677f  mov     dword ptr [rsp+140h+phkResult], 3
0x180026787  call    Reg_GetValueEx2
0x18002678c  test    eax, eax
0x18002678e  jnz     loc_180026906
0x180026794  mov     rdx, [rbp+30h+hKey]
0x180026798  lea     rax, [rbp+30h+var_70]
0x18002679c  mov     [rsp+140h+var_110], rax
0x1800267a1  mov     r9d, 7Eh ; '~'
0x1800267a7  mov     dword ptr [rsp+140h+phkResult], 3
0x1800267af  call    Reg_GetValueEx2
0x1800267b4  test    eax, eax
0x1800267b6  jnz     loc_180026906
0x1800267bc  mov     rdx, [rbp+30h+hKey]
0x1800267c0  lea     rax, [rbp+30h+var_54]
0x1800267c4  mov     [rsp+140h+var_110], rax
0x1800267c9  mov     r9d, 89h
0x1800267cf  mov     dword ptr [rsp+140h+phkResult], 4
0x1800267d7  call    Reg_GetValueEx2
0x1800267dc  test    eax, eax
0x1800267de  jnz     loc_180026906
0x1800267e4  mov     rdx, [rbp+30h+hKey]
0x1800267e8  lea     rax, [rbp+30h+var_50]
0x1800267ec  mov     [rsp+140h+var_110], rax
0x1800267f1  mov     r9d, 8Ah
0x1800267f7  mov     dword ptr [rsp+140h+phkResult], 4
0x1800267ff  call    Reg_GetValueEx2
0x180026804  test    eax, eax
0x180026806  jnz     loc_180026906
0x18002680c  mov     r8, [rbp+30h+var_80]
0x180026810  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026814  test    r8, r8
0x180026817  jz      short loc_18002682F
0x180026819  mov     rax, rcx
0x18002681c  inc     rax
0x18002681f  cmp     [r8+rax*2], r14w
0x180026824  jnz     short loc_18002681C
0x180026826  neg     rax
0x180026829  sbb     rax, rax
0x18002682c  and     r8, rax
0x18002682f  mov     r9, [rbp+30h+var_78]
0x180026833  test    r9, r9
0x180026836  jz      short loc_18002684B
0x180026838  inc     rcx
0x18002683b  cmp     [r9+rcx*2], r14w
0x180026840  jnz     short loc_180026838
0x180026842  neg     rcx
0x180026845  sbb     rax, rax
0x180026848  and     r9, rax
0x18002684b  mov     eax, edi
0x18002684d  neg     eax
0x18002684f  mov     eax, esi
0x180026851  sbb     ecx, ecx
0x180026853  and     ecx, 8
0x180026856  neg     eax
0x180026858  sbb     edx, edx
0x18002685a  and     edx, 8
0x18002685d  test    esi, esi
0x18002685f  jnz     short loc_180026868
0x180026861  mov     eax, r14d
0x180026864  test    edi, edi
0x180026866  jz      short loc_18002686D
0x180026868  mov     eax, 8
0x18002686d  lea     r10, [rbp+30h+var_98]
0x180026871  mov     [rsp+140h+var_C0], r10; __int64
0x180026879  mov     [rsp+140h+var_C8], r14; __int64
0x18002687e  mov     r14, [rbp+30h+var_A8]
0x180026882  mov     [rsp+140h+var_D8], ecx; int
0x180026886  mov     rcx, r15; Src
0x180026889  mov     [rsp+140h+var_E0], edx; int
0x18002688d  mov     rdx, [rbp+30h+var_88]; void *
0x180026891  mov     [rsp+140h+var_E8], eax; int
0x180026895  mov     eax, [rbp+30h+var_54]
0x180026898  mov     [rsp+140h+var_F0], eax; int
0x18002689c  mov     eax, dword ptr [rbp+30h+var_50]
0x18002689f  mov     [rsp+140h+var_F8], eax; int
0x1800268a3  mov     rax, [rbp+30h+var_68]
0x1800268a7  mov     [rsp+140h+var_100], rax; __int64
0x1800268ac  mov     rax, [rbp+30h+var_70]
0x1800268b0  mov     [rsp+140h+var_108], rax; __int64
0x1800268b5  mov     rax, [rbp+30h+var_A0]
0x1800268b9  mov     [rsp+140h+var_110], r14; void *
0x1800268be  mov     [rsp+140h+var_118], rax; void *
0x1800268c3  mov     [rsp+140h+phkResult], rbx; void *
0x1800268c8  call    areg_AllocateEntry
0x1800268cd  test    eax, eax
0x1800268cf  jz      short loc_1800268D6
0x1800268d1  xor     r12d, r12d
0x1800268d4  jmp     short loc_18002690A
0x1800268d6  mov     rbx, [rbp+30h+var_98]
0x1800268da  mov     eax, [rbp+30h+var_B0]
0x1800268dd  mov     dword ptr [rbx+100h], 1
0x1800268e7  mov     [rbx+10Ch], r13d
0x1800268ee  mov     [rbx+108h], r12d
0x1800268f5  mov     [rbx+114h], eax
0x1800268fb  mov     eax, [rbp+30h+var_AC]
0x1800268fe  mov     [rbx+118h], eax
0x180026904  jmp     short loc_18002690A
0x180026906  mov     r14, [rbp+30h+var_A8]
0x18002690a  mov     rcx, [rbp+30h+hKey]; hKey
0x18002690e  test    rcx, rcx
0x180026911  jz      short loc_180026919
0x180026913  call    cs:__imp_RegCloseKey
0x180026919  mov     rcx, [rbp+30h+var_A0]; void *
0x18002691d  call    MIDL_user_free
0x180026922  mov     rcx, r14; void *
0x180026925  call    MIDL_user_free
0x18002692a  mov     rcx, [rbp+30h+var_88]; void *
0x18002692e  call    MIDL_user_free
0x180026933  mov     rcx, [rbp+30h+var_80]; void *
0x180026937  call    MIDL_user_free
0x18002693c  mov     rcx, [rbp+30h+var_78]; void *
0x180026940  call    MIDL_user_free
0x180026945  mov     rcx, [rbp+30h+var_70]; void *
0x180026949  call    MIDL_user_free
0x18002694e  mov     rcx, [rbp+30h+var_68]; void *
0x180026952  call    MIDL_user_free
0x180026957  mov     rdx, rbx
0x18002695a  lea     rcx, aLeavingAregRea; "Leaving areg_ReadEntryFromRegistry:"
0x180026961  call    areg_LogEntry
0x180026966  mov     rdx, rbx
0x180026969  lea     rcx, aLeaveAregReade; "Leave areg_ReadEntryFromRegistry():"
0x180026970  call    DnsPrint_AregEntry
0x180026975  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002697c  jz      short loc_1800269A1
0x18002697e  mov     r9d, [rbp+30h+var_60]
0x180026982  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180026989  mov     dword ptr [rsp+140h+phkResult], r9d
0x18002698e  mov     edx, 59h ; 'Y'
0x180026993  mov     r9d, [rbp+30h+var_5C]
0x180026997  mov     ecx, 40Bh
0x18002699c  call    WPP_SF_dd
0x1800269a1  mov     rax, rbx
0x1800269a4  mov     rcx, [rbp+30h+var_48]
0x1800269a8  xor     rcx, rsp; StackCookie
0x1800269ab  call    __security_check_cookie
0x1800269b0  add     rsp, 108h
0x1800269b7  pop     r15
0x1800269b9  pop     r14
0x1800269bb  pop     r13
0x1800269bd  pop     r12
0x1800269bf  pop     rdi
  ... truncated ...
```
