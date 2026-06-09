# CreatePersistedRegistryKeyHelper

- ea: `0x1800097e0`
- end: `0x180009afe`
- name: `CreatePersistedRegistryKeyHelper`
- size: `798`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180007cfc`
- `0x1800096d0`
- `0x180041e00`
- `0x180075ec8`
- `0x18007d84c`
- `0x1800841bc`
- `0x1800951e0`
- `0x180095740`
- `0x1800a47bc`
- `0x1800ab380`

## callees

- `0x1800097e0`
- `0x18007f24c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cccb0`
- `0x1800dbb48`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800099d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800099d0`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009864`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009864`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180009963`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180009963`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180009ae6`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180009ae6`

## pseudocode

```c
__int64 __fastcall CreatePersistedRegistryKeyHelper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        _QWORD *a8)
{
  int v11; // edx
  int v12; // ecx
  int v13; // r8d
  int PersistedStateLocation; // eax
  int v15; // edx
  _WORD *v16; // rcx
  int v17; // r8d
  int v18; // ebx
  int v19; // ebx
  _WORD *v20; // r9
  unsigned __int64 v21; // r8
  __int64 v22; // rcx
  _WORD *v23; // rdx
  ULONG v24; // edi
  ULONG Key; // eax
  _DWORD v27[4]; // [rsp+50h] [rbp-268h] BYREF
  _WORD v28[264]; // [rsp+60h] [rbp-258h] BYREF

  memset_0(v28, 0, 0x20Au);
  *a8 = 0;
  v27[0] = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_SSSqd(v12, v11, v13, a1, a2, a3, (__int64)v28, 10);
  PersistedStateLocation = RtlGetPersistedStateLocation(a1, 0, a2, 0, v28, 522, v27);
  v18 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSd((_DWORD)v16, v15, v17, a1, a2, a3, PersistedStateLocation);
    v19 = HRESULT_FROM_NTSTATUS(v18);
  }
  else
  {
    v19 = 0;
    if ( a3 )
    {
      LODWORD(v16) = v27[0];
      v20 = &v28[(unsigned __int64)v27[0] >> 1];
      v21 = (unsigned __int64)(unsigned int)(522 - v27[0]) >> 1;
      *(v20 - 1) = 92;
      if ( v21 )
      {
        v22 = 2147483646;
        v23 = (_WORD *)a3;
        do
        {
          if ( !v22 )
            break;
          if ( !*v23 )
            break;
          *v20++ = *v23++;
          --v22;
          --v21;
        }
        while ( v21 );
        v16 = v20 - 1;
        v19 = -2147024774;
        if ( v21 )
        {
          v16 = v20;
          v19 = 0;
        }
        *v16 = 0;
        if ( v19 >= 0 )
        {
          if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
            goto LABEL_14;
          WPP_SF_SSSS((_DWORD)v16, (_DWORD)v23, v21, a1, a2, a3, (__int64)v28);
          goto LABEL_35;
        }
      }
      else
      {
        v19 = -2147024809;
      }
      if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
        goto LABEL_14;
      WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v19);
    }
  }
LABEL_35:
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v19);
LABEL_14:
  if ( v19 >= 0 )
  {
    if ( a7 )
      Key = RegCreateKeyExInternalW(-2147483646, v28, 0, 0, 0, a5, 0, a8, 0, 0);
    else
      Key = RegOpenKeyExInternalW(-2147483646, v28, 0, a5, a8, 0);
    v24 = Key;
  }
  else if ( (v19 & 0x1FFF0000) == 0xC0000 )
  {
    v24 = (unsigned __int16)v19;
  }
  else if ( (v19 & 0x1FFF0000) == 0x70000 )
  {
    v24 = (unsigned __int16)v19;
    if ( !(_WORD)v19 )
      v24 = 317;
  }
  else if ( (v19 & 0x10000000) != 0 )
  {
    v24 = RtlNtStatusToDosError(v19 & 0xEFFFFFFF);
    if ( v24 )
    {
      if ( v24 == 317 )
        v24 = v19;
    }
    else
    {
      v24 = v19;
    }
  }
  else
  {
    v24 = v19;
  }
  if ( v24 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_SD((_DWORD)v16, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v28, v24);
  return v24;
}

```

## disassembly

```asm
0x1800097e0  push    rbx
0x1800097e2  push    rbp
0x1800097e3  push    rsi
0x1800097e4  push    rdi
0x1800097e5  push    r12
0x1800097e7  push    r14
0x1800097e9  push    r15
0x1800097eb  sub     rsp, 280h
0x1800097f2  mov     rax, cs:__security_cookie
0x1800097f9  xor     rax, rsp
0x1800097fc  mov     [rsp+2B8h+var_48], rax
0x180009804  mov     r15, [rsp+2B8h+arg_38]
0x18000980c  mov     rsi, r8
0x18000980f  mov     r14, rdx
0x180009812  mov     rbp, rcx
0x180009815  mov     edi, 20Ah
0x18000981a  lea     rcx, [rsp+2B8h+var_258]; void *
0x18000981f  mov     r8d, edi; Size
0x180009822  xor     edx, edx; Val
0x180009824  call    memset_0
0x180009829  xor     r12d, r12d
0x18000982c  mov     [r15], r12
0x18000982f  mov     [rsp+2B8h+var_268], r12d
0x180009834  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18000983b  jnz     loc_180009A45
0x180009841  lea     rax, [rsp+2B8h+var_268]
0x180009846  xor     r9d, r9d
0x180009849  mov     [rsp+2B8h+var_288], rax
0x18000984e  mov     r8, r14
0x180009851  lea     rax, [rsp+2B8h+var_258]
0x180009856  mov     dword ptr [rsp+2B8h+var_290], edi
0x18000985a  xor     edx, edx
0x18000985c  mov     [rsp+2B8h+var_298], rax
0x180009861  mov     rcx, rbp
0x180009864  call    cs:__imp_RtlGetPersistedStateLocation
0x18000986b  nop     dword ptr [rax+rax+00h]
0x180009870  mov     ebx, eax
0x180009872  test    eax, eax
0x180009874  js      loc_180009A6A
0x18000987a  mov     ebx, r12d
0x18000987d  test    rsi, rsi
0x180009880  jz      loc_180009A1A
0x180009886  mov     ecx, [rsp+2B8h+var_268]
0x18000988a  lea     r9, [rsp+2B8h+var_258]
0x18000988f  sub     edi, ecx
0x180009891  mov     eax, ecx
0x180009893  shr     rax, 1
0x180009896  mov     r8d, edi
0x180009899  lea     r9, [r9+rax*2]
0x18000989d  shr     r8, 1
0x1800098a0  mov     word ptr [r9-2], 5Ch ; '\'
0x1800098a7  jz      loc_180009AF7
0x1800098ad  mov     ecx, 7FFFFFFEh
0x1800098b2  mov     rdx, rsi
0x1800098b5  test    rcx, rcx
0x1800098b8  jz      short loc_1800098D7
0x1800098ba  movzx   eax, word ptr [rdx]
0x1800098bd  test    ax, ax
0x1800098c0  jz      short loc_1800098D7
0x1800098c2  mov     [r9], ax
0x1800098c6  add     rdx, 2
0x1800098ca  add     r9, 2
0x1800098ce  dec     rcx
0x1800098d1  sub     r8, 1
0x1800098d5  jnz     short loc_1800098B5
0x1800098d7  test    r8, r8
0x1800098da  lea     rcx, [r9-2]
0x1800098de  mov     ebx, 8007007Ah
0x1800098e3  cmovnz  rcx, r9
0x1800098e7  cmovnz  ebx, r12d
0x1800098eb  mov     [rcx], r12w
0x1800098ef  test    ebx, ebx
0x1800098f1  js      loc_180009A94
0x1800098f7  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x1800098fe  jnz     loc_1800099FE
0x180009904  test    ebx, ebx
0x180009906  jns     short loc_180009934
0x180009908  mov     eax, ebx
0x18000990a  and     eax, 1FFF0000h
0x18000990f  cmp     eax, 0C0000h
0x180009914  jz      loc_1800099BF
0x18000991a  cmp     eax, 70000h
0x18000991f  jnz     loc_1800099C4
0x180009925  movzx   edi, bx
0x180009928  mov     eax, 13Dh
0x18000992d  test    edi, edi
0x18000992f  cmovz   edi, eax
0x180009932  jmp     short loc_180009971
0x180009934  xor     r8d, r8d
0x180009937  lea     rdx, [rsp+2B8h+var_258]
0x18000993c  mov     rcx, 0FFFFFFFF80000002h
0x180009943  cmp     [rsp+2B8h+arg_30], r12d
0x18000994b  jnz     loc_180009ABF
0x180009951  mov     r9d, [rsp+2B8h+arg_20]
0x180009959  mov     [rsp+2B8h+var_290], r12
0x18000995e  mov     [rsp+2B8h+var_298], r15
0x180009963  call    cs:__imp_RegOpenKeyExInternalW
0x18000996a  nop     dword ptr [rax+rax+00h]
0x18000996f  mov     edi, eax
0x180009971  test    edi, edi
0x180009973  jnz     short loc_18000999A
0x180009975  mov     eax, edi
0x180009977  mov     rcx, [rsp+2B8h+var_48]
0x18000997f  xor     rcx, rsp; StackCookie
0x180009982  call    __security_check_cookie
0x180009987  add     rsp, 280h
0x18000998e  pop     r15
0x180009990  pop     r14
0x180009992  pop     r12
0x180009994  pop     rdi
0x180009995  pop     rsi
0x180009996  pop     rbp
0x180009997  pop     rbx
0x180009998  retn
0x18000999a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800099a1  jz      short loc_180009975
0x1800099a3  mov     edx, 0Ah
0x1800099a8  mov     dword ptr [rsp+2B8h+var_298], edi
0x1800099ac  lea     r9, [rsp+2B8h+var_258]
0x1800099b1  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x1800099b8  call    WPP_SF_SD
0x1800099bd  jmp     short loc_180009975
0x1800099bf  movzx   edi, bx
0x1800099c2  jmp     short loc_180009971
0x1800099c4  bt      ebx, 1Ch
0x1800099c8  jnb     short loc_1800099E6
0x1800099ca  mov     ecx, ebx
0x1800099cc  btr     ecx, 1Ch; Status
0x1800099d0  call    cs:__imp_RtlNtStatusToDosError
0x1800099d7  nop     dword ptr [rax+rax+00h]
0x1800099dc  mov     edi, eax
0x1800099de  test    eax, eax
0x1800099e0  jnz     short loc_1800099EA
0x1800099e2  mov     edi, ebx
0x1800099e4  jmp     short loc_180009971
0x1800099e6  mov     edi, ebx
0x1800099e8  jmp     short loc_180009971
0x1800099ea  mov     eax, 13Dh
0x1800099ef  cmp     edi, eax
0x1800099f1  jnz     loc_180009971
0x1800099f7  mov     edi, ebx
0x1800099f9  jmp     loc_180009971
0x1800099fe  lea     rax, [rsp+2B8h+var_258]
0x180009a03  mov     r9, rbp
0x180009a06  mov     [rsp+2B8h+var_288], rax
0x180009a0b  mov     [rsp+2B8h+var_290], rsi
0x180009a10  mov     [rsp+2B8h+var_298], r14
0x180009a15  call    WPP_SF_SSSS
0x180009a1a  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180009a21  jz      loc_180009904
0x180009a27  mov     edx, 0Eh
0x180009a2c  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180009a33  mov     ecx, 41Dh
0x180009a38  mov     r9d, ebx
0x180009a3b  call    WPP_SF_d
0x180009a40  jmp     loc_180009904
0x180009a45  mov     dword ptr [rsp+2B8h+var_280], edi
0x180009a49  lea     rax, [rsp+2B8h+var_258]
0x180009a4e  mov     [rsp+2B8h+var_288], rax
0x180009a53  mov     r9, rbp
0x180009a56  mov     [rsp+2B8h+var_290], rsi
0x180009a5b  mov     [rsp+2B8h+var_298], r14
0x180009a60  call    WPP_SF_SSSqd
0x180009a65  jmp     loc_180009841
0x180009a6a  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180009a71  jz      short loc_180009A89
0x180009a73  mov     dword ptr [rsp+2B8h+var_288], ebx
0x180009a77  mov     r9, rbp
0x180009a7a  mov     [rsp+2B8h+var_290], rsi
0x180009a7f  mov     [rsp+2B8h+var_298], r14
0x180009a84  call    WPP_SF_SSSd
0x180009a89  mov     ecx, ebx; int
0x180009a8b  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x180009a90  mov     ebx, eax
0x180009a92  jmp     short loc_180009A1A
0x180009a94  mov     r9d, ebx
0x180009a97  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180009a9e  jz      loc_180009904
0x180009aa4  mov     edx, 0Ch
0x180009aa9  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180009ab0  mov     ecx, 41Dh
0x180009ab5  call    WPP_SF_d
0x180009aba  jmp     loc_180009A1A
0x180009abf  mov     eax, [rsp+2B8h+arg_20]
0x180009ac6  xor     r9d, r9d
0x180009ac9  mov     [rsp+2B8h+var_270], r12
0x180009ace  mov     [rsp+2B8h+var_278], r12
0x180009ad3  mov     [rsp+2B8h+var_280], r15
0x180009ad8  mov     [rsp+2B8h+var_288], r12
0x180009add  mov     dword ptr [rsp+2B8h+var_290], eax
0x180009ae1  mov     dword ptr [rsp+2B8h+var_298], r12d
0x180009ae6  call    cs:__imp_RegCreateKeyExInternalW
0x180009aed  nop     dword ptr [rax+rax+00h]
0x180009af2  jmp     loc_18000996F
0x180009af7  mov     ebx, 80070057h
0x180009afc  jmp     short loc_180009A94
```
