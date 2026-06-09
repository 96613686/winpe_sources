# DriverProc(ulong,HDRVR__ *,uint,unsigned __int64,unsigned __int64)

- ea: `0x1800044b0`
- end: `0x18000460b`
- name: `?DriverProc@@YA_JKPEAUHDRVR__@@I_K1@Z`
- size: `347`
- prototype: `LRESULT __fastcall(LPARAM lParam, HDRVR hDriver, UINT, LPARAM, struct tagMCI_GENERIC_PARMS *lParam2)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800044b0`
- `0x18000485c`

## import_xrefs

- `WINMM!DefDriverProc` at `0x18000454a`
- `WINMM!DefDriverProc` at `0x18000454a`
- `WINMM!mciGetDriverData` at `0x18000451b`
- `WINMM!mciGetDriverData` at `0x18000451b`
- `WINMM!GetDriverModuleHandle` at `0x1800045c0`
- `WINMM!GetDriverModuleHandle` at `0x1800045c0`
- `WINMM!mciLoadCommandResource` at `0x1800045f5`
- `WINMM!mciLoadCommandResource` at `0x1800045f5`
- `WINMM!mciFreeCommandResource` at `0x180004572`
- `WINMM!mciFreeCommandResource` at `0x180004572`
- `ole32!CoUninitialize` at `0x180004582`
- `ole32!CoUninitialize` at `0x180004582`
- `ole32!CoInitializeEx` at `0x1800045d4`
- `ole32!CoInitializeEx` at `0x1800045d4`

## pseudocode

```c
LRESULT __fastcall DriverProc(LPARAM lParam, HDRVR hDriver, UINT a3, LPARAM a4, struct MCI_DGV_UPDATE_PARMS *lParam2)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  struct _MCIGRAPHIC *DriverData; // rax
  LRESULT result; // rax

  v5 = lParam;
  v6 = a4;
  switch ( a3 )
  {
    case 1u:
      ghModule = GetDriverModuleHandle(hDriver);
      if ( CoInitializeEx(0, 2u) < 0 )
        return 0;
      wTable = mciLoadCommandResource(ghModule, L"MCIAVI", 0);
      return 1;
    case 2u:
      return 1;
    case 3u:
      if ( !lParam2 )
        return 10000;
      lParam2->rc.top = wTable;
      result = LODWORD(lParam2->dwCallback);
      lParam2->rc.right = 520;
      return result;
    case 4u:
    case 5u:
      return 1;
  }
  if ( a3 != 6 )
  {
    if ( a3 != 8 )
    {
      if ( WORD1(lParam) || a3 - 2048 > 0xFFF )
        return DefDriverProc((unsigned int)lParam, hDriver, a3, a4, (LPARAM)lParam2);
      DriverData = (struct _MCIGRAPHIC *)mciGetDriverData(lParam);
      return mciDriverEntry(DriverData, v5, a3, v6, lParam2);
    }
    return 0;
  }
  if ( wTable != -1 )
  {
    mciFreeCommandResource(wTable);
    wTable = -1;
  }
  CoUninitialize();
  result = 1;
  ghModule = 0;
  return result;
}

```

## disassembly

```asm
0x1800044b0  mov     [rsp+arg_0], rbx
0x1800044b5  mov     [rsp+arg_8], rsi
0x1800044ba  push    rdi
0x1800044bb  sub     rsp, 30h
0x1800044bf  mov     eax, r8d
0x1800044c2  mov     edi, ecx
0x1800044c4  mov     rsi, r9
0x1800044c7  mov     ebx, r8d
0x1800044ca  sub     eax, 1
0x1800044cd  jz      loc_1800045BD
0x1800044d3  sub     eax, 1
0x1800044d6  jz      loc_180004601
0x1800044dc  sub     eax, 1
0x1800044df  jz      loc_180004598
0x1800044e5  sub     eax, 1
0x1800044e8  jz      loc_180004601
0x1800044ee  sub     eax, 1
0x1800044f1  jz      loc_180004601
0x1800044f7  sub     eax, 1
0x1800044fa  jz      short loc_180004567
0x1800044fc  cmp     eax, 2
0x1800044ff  jz      short loc_180004552
0x180004501  mov     eax, edi
0x180004503  shr     eax, 10h
0x180004506  test    ax, ax
0x180004509  jnz     short loc_18000453D
0x18000450b  lea     eax, [r8-800h]
0x180004512  cmp     eax, 0FFFh
0x180004517  ja      short loc_18000453D
0x180004519  mov     ecx, edi; wDeviceID
0x18000451b  call    cs:__imp_mciGetDriverData
0x180004521  mov     rcx, [rsp+38h+arg_20]
0x180004526  mov     r9d, esi; unsigned int
0x180004529  mov     [rsp+38h+lParam2], rcx; struct tagMCI_GENERIC_PARMS *
0x18000452e  mov     r8d, ebx; unsigned int
0x180004531  mov     rcx, rax; struct _MCIGRAPHIC *
0x180004534  mov     edx, edi; lParam
0x180004536  call    ?mciDriverEntry@@YA_KPEAU_MCIGRAPHIC@@IIKPEAUtagMCI_GENERIC_PARMS@@@Z; mciDriverEntry(_MCIGRAPHIC *,uint,uint,ulong,tagMCI_GENERIC_PARMS *)
0x18000453b  jmp     short loc_180004557
0x18000453d  mov     rax, [rsp+38h+arg_20]
0x180004542  mov     rcx, rdi; dwDriverIdentifier
0x180004545  mov     [rsp+38h+lParam2], rax; lParam2
0x18000454a  call    cs:__imp_DefDriverProc
0x180004550  jmp     short loc_180004557
0x180004552  xor     ecx, ecx
0x180004554  mov     rax, rcx
0x180004557  mov     rbx, [rsp+38h+arg_0]
0x18000455c  mov     rsi, [rsp+38h+arg_8]
0x180004561  add     rsp, 30h
0x180004565  pop     rdi
0x180004566  retn
0x180004567  mov     ecx, cs:wTable; wTable
0x18000456d  cmp     ecx, 0FFFFFFFFh
0x180004570  jz      short loc_180004582
0x180004572  call    cs:__imp_mciFreeCommandResource
0x180004578  mov     cs:wTable, 0FFFFFFFFh
0x180004582  call    cs:__imp_CoUninitialize
0x180004588  xor     ecx, ecx
0x18000458a  mov     eax, 1
0x18000458f  mov     cs:?ghModule@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * ghModule
0x180004596  jmp     short loc_180004557
0x180004598  mov     rdx, [rsp+38h+arg_20]
0x18000459d  test    rdx, rdx
0x1800045a0  jnz     short loc_1800045A9
0x1800045a2  mov     eax, 2710h
0x1800045a7  jmp     short loc_180004557
0x1800045a9  mov     eax, cs:wTable
0x1800045af  mov     [rdx+0Ch], eax
0x1800045b2  mov     eax, [rdx]
0x1800045b4  mov     dword ptr [rdx+10h], 208h
0x1800045bb  jmp     short loc_180004557
0x1800045bd  mov     rcx, rdx; hDriver
0x1800045c0  call    cs:__imp_GetDriverModuleHandle
0x1800045c6  mov     edx, 2; dwCoInit
0x1800045cb  xor     ecx, ecx; pvReserved
0x1800045cd  mov     cs:?ghModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghModule
0x1800045d4  call    cs:__imp_CoInitializeEx
0x1800045da  xor     ecx, ecx
0x1800045dc  test    eax, eax
0x1800045de  js      loc_180004554
0x1800045e4  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; hInstance
0x1800045eb  lea     rdx, ResName; "MCIAVI"
0x1800045f2  xor     r8d, r8d; wType
0x1800045f5  call    cs:__imp_mciLoadCommandResource
0x1800045fb  mov     cs:wTable, eax
0x180004601  mov     eax, 1
0x180004606  jmp     loc_180004557
```
