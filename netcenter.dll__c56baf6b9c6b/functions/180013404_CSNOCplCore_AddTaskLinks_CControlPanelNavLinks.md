# CSNOCplCore::_AddTaskLinks(CControlPanelNavLinks *)

- ea: `0x180013404`
- end: `0x180013599`
- name: `?_AddTaskLinks@CSNOCplCore@@AEAAJPEAVCControlPanelNavLinks@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct CControlPanelNavLinks *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800091ec`

## callees

- `0x180002270`
- `0x180008720`
- `0x180013404`
- `0x18001c738`
- `0x18001c824`
- `0x18001c980`
- `0x18001c998`
- `0x18001c9bc`
- `0x18001c9d4`
- `0x180021dfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetPSClsid` at `0x180013495`
- `api-ms-win-core-com-l1-1-0!CoGetPSClsid` at `0x180013495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013558`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001347d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001347d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001346b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001346b`

## string_xrefs

- `0x18001345d`: `CLSID\{5d1026ee-3f2e-4ccb-a83d-cefb7ac22a71}`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::_AddTaskLinks(CSNOCplCore *this, struct CControlPanelNavLinks *a2)
{
  unsigned int i; // edi
  __int64 v4; // rbx
  int v5; // r8d
  int v6; // edx
  int v7; // eax
  unsigned int v8; // edx
  CControlPanelNavLink *v9; // rbx
  const unsigned __int16 *v10; // r8
  bool v11; // r9
  __int64 v12; // rax
  int v13; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  CLSID pClsid; // [rsp+40h] [rbp-20h] BYREF

  for ( i = 0; i < 3; ++i )
  {
    v4 = 32LL * i;
    if ( *(_DWORD *)((char *)&unk_180024360 + v4) == 199 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{5d1026ee-3f2e-4ccb-a83d-cefb7ac22a71}", 0, 1u, &hKey) )
        continue;
      RegCloseKey(hKey);
      pClsid = 0;
      if ( CoGetPSClsid(&GUID_01f5f85e_0a81_40da_a7c8_21ef3af8440c, &pClsid) < 0 )
        continue;
    }
    hKey = 0;
    if ( (int)CControlPanelNavLink::Create(0, &hKey) >= 0 )
    {
      v6 = *(_DWORD *)((char *)&unk_180024360 + v4);
      pv = 0;
      v7 = TResourceStringAllocCopyEx<unsigned short *>(
             (int)g_hinst,
             v6,
             v5,
             (int)&ResourceStringAllocCopyExCoAlloc,
             phkResult,
             &pv);
      v9 = (CControlPanelNavLink *)hKey;
      if ( v7 >= 0 )
      {
        if ( (int)CControlPanelNavLink::SetName((CControlPanelNavLink *)hKey, (const unsigned __int16 *)pv) >= 0 )
        {
          v12 = 32LL * (int)i;
          if ( *(_QWORD *)((char *)&unk_180024360 + v12 + 8) )
            v13 = CControlPanelNavLink::SetCommandNotify(v9, i + 1);
          else
            v13 = *(_DWORD *)((char *)&unk_180024360 + v12 + 16)
                ? CControlPanelNavLink::SetCommandControlPanel(
                    v9,
                    L"Microsoft.NetworkAndSharingCenter",
                    *(const unsigned __int16 **)((char *)&unk_180024360 + v12 + 24),
                    v11)
                : CControlPanelNavLink::SetCommandShellEx(
                    v9,
                    *(const unsigned __int16 **)((char *)&unk_180024360 + v12 + 24),
                    v10);
          if ( v13 >= 0 && (int)CControlPanelNavLinks::Add(a2, v9) >= 0 )
            v9 = 0;
        }
        CoTaskMemFree(pv);
      }
      if ( v9 )
        CControlPanelNavLink::`scalar deleting destructor'(v9, v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013404  mov     [rsp-18h+arg_0], rbx
0x180013409  mov     [rsp-18h+arg_10], rsi
0x18001340e  push    rbp
0x18001340f  push    rdi
0x180013410  push    r15
0x180013412  mov     rbp, rsp
0x180013415  sub     rsp, 60h
0x180013419  mov     rax, cs:__security_cookie
0x180013420  xor     rax, rsp
0x180013423  mov     [rbp+var_10], rax
0x180013427  mov     rsi, rdx
0x18001342a  lea     r15, unk_180024360
0x180013431  xor     edi, edi
0x180013433  mov     ebx, edi
0x180013435  shl     rbx, 5
0x180013439  cmp     dword ptr [rbx+r15], 0C7h
0x180013441  jnz     short loc_1800134A3
0x180013443  lea     rax, [rbp+hKey]
0x180013447  mov     [rbp+hKey], 0
0x18001344f  mov     r9d, 1; samDesired
0x180013455  mov     [rsp+60h+phkResult], rax; Src
0x18001345a  xor     r8d, r8d; ulOptions
0x18001345d  lea     rdx, SubKey; "CLSID\\{5d1026ee-3f2e-4ccb-a83d-cefb7ac"...
0x180013464  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001346b  call    cs:__imp_RegOpenKeyExW
0x180013471  test    eax, eax
0x180013473  jnz     loc_18001356B
0x180013479  mov     rcx, [rbp+hKey]; hKey
0x18001347d  call    cs:__imp_RegCloseKey
0x180013483  xorps   xmm0, xmm0
0x180013486  lea     rdx, [rbp+pClsid]; pClsid
0x18001348a  lea     rcx, _GUID_01f5f85e_0a81_40da_a7c8_21ef3af8440c; riid
0x180013491  movups  xmmword ptr [rbp+pClsid.Data1], xmm0
0x180013495  call    cs:__imp_CoGetPSClsid
0x18001349b  test    eax, eax
0x18001349d  js      loc_18001356B
0x1800134a3  lea     rdx, [rbp+hKey]
0x1800134a7  mov     [rbp+hKey], 0
0x1800134af  xor     ecx, ecx
0x1800134b1  call    ?Create@CControlPanelNavLink@@SAJW4CPNAV_LIST@@PEAPEAV1@@Z; CControlPanelNavLink::Create(CPNAV_LIST,CControlPanelNavLink * *)
0x1800134b6  test    eax, eax
0x1800134b8  js      loc_18001356B
0x1800134be  mov     edx, [rbx+r15]; int
0x1800134c2  lea     rax, [rbp+pv]
0x1800134c6  mov     rcx, cs:g_hinst; int
0x1800134cd  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800134d4  mov     [rsp+60h+var_38], rax; void *
0x1800134d9  mov     [rbp+pv], 0
0x1800134e1  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800134e6  mov     rbx, [rbp+hKey]
0x1800134ea  test    eax, eax
0x1800134ec  js      short loc_18001355E
0x1800134ee  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800134f2  mov     rcx, rbx; this
0x1800134f5  call    ?SetName@CControlPanelNavLink@@QEAAJPEBG@Z; CControlPanelNavLink::SetName(ushort const *)
0x1800134fa  test    eax, eax
0x1800134fc  js      short loc_180013554
0x1800134fe  movsxd  rax, edi
0x180013501  mov     rcx, rbx; this
0x180013504  shl     rax, 5
0x180013508  cmp     qword ptr [rax+r15+8], 0
0x18001350e  jz      short loc_18001351A
0x180013510  lea     edx, [rdi+1]; int
0x180013513  call    ?SetCommandNotify@CControlPanelNavLink@@QEAAJH@Z; CControlPanelNavLink::SetCommandNotify(int)
0x180013518  jmp     short loc_18001353D
0x18001351a  cmp     dword ptr [rax+r15+10h], 0
0x180013520  mov     rdx, [rax+r15+18h]; unsigned __int16 *
0x180013525  jz      short loc_180013538
0x180013527  mov     r8, rdx; unsigned __int16 *
0x18001352a  lea     rdx, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x180013531  call    ?SetCommandControlPanel@CControlPanelNavLink@@QEAAJPEBG0_N@Z; CControlPanelNavLink::SetCommandControlPanel(ushort const *,ushort const *,bool)
0x180013536  jmp     short loc_18001353D
0x180013538  call    ?SetCommandShellEx@CControlPanelNavLink@@QEAAJPEBG0@Z; CControlPanelNavLink::SetCommandShellEx(ushort const *,ushort const *)
0x18001353d  test    eax, eax
0x18001353f  js      short loc_180013554
0x180013541  mov     rdx, rbx; struct CControlPanelNavLink *
0x180013544  mov     rcx, rsi; this
0x180013547  call    ?Add@CControlPanelNavLinks@@QEAAJPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::Add(CControlPanelNavLink *)
0x18001354c  xor     edx, edx
0x18001354e  test    eax, eax
0x180013550  cmovns  rbx, rdx
0x180013554  mov     rcx, [rbp+pv]; pv
0x180013558  call    cs:__imp_CoTaskMemFree
0x18001355e  test    rbx, rbx
0x180013561  jz      short loc_18001356B
0x180013563  mov     rcx, rbx; this
0x180013566  call    ??_GCControlPanelNavLink@@QEAAPEAXI@Z; CControlPanelNavLink::`scalar deleting destructor'(uint)
0x18001356b  inc     edi
0x18001356d  cmp     edi, 3
0x180013570  jb      loc_180013433
0x180013576  xor     eax, eax
0x180013578  mov     rcx, [rbp+var_10]
0x18001357c  xor     rcx, rsp; StackCookie
0x18001357f  call    __security_check_cookie
0x180013584  lea     r11, [rsp+60h+var_s0]
0x180013589  mov     rbx, [r11+20h]
0x18001358d  mov     rsi, [r11+30h]
0x180013591  mov     rsp, r11
0x180013594  pop     r15
0x180013596  pop     rdi
0x180013597  pop     rbp
0x180013598  retn
```
