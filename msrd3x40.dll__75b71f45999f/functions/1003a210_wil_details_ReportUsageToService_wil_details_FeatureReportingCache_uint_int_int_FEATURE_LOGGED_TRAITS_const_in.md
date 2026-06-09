# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)

- ea: `0x1003a210`
- end: `0x1003a302`
- name: `?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z`
- size: `242`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1003fc40`
- `0x1003fcc0`
- `0x1003fd40`
- `0x1003fdc0`
- `0x1003fe40`
- `0x1003fec0`
- `0x1003ff40`
- `0x10041060`
- `0x100411f0`
- `0x10041360`
- `0x100414d0`
- `0x10041640`
- `0x100417b0`

## callees

- `0x1000eb60`
- `0x1003a060`
- `0x1003a210`

## pseudocode

```c
int __fastcall wil::details::ReportUsageToService(
        int a1,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8)
{
  int result; // eax
  int v10; // ecx
  int v11; // ecx

  result = a7;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 0:
        goto LABEL_15;
      case 1:
        v10 = 4;
        if ( a6 )
          v10 = 0;
        break;
      case 2:
        v10 = 4 * (a6 == 0) + 1;
        break;
      case 3:
        v10 = 4 * (a6 == 0) + 2;
        break;
      case 4:
        v10 = 4 * (a6 == 0) + 3;
        break;
      case 5:
        v10 = 2 * (a6 == 0) + 8;
        break;
      case 6:
        v10 = 2 * (a6 == 0) + 9;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
        {
LABEL_15:
          v10 = 255;
        }
        else
        {
          v11 = 100;
          if ( !a6 )
            v11 = 150;
          v10 = (unsigned __int8)(a7 - 100) + v11;
        }
        break;
    }
    result = ((int (__thiscall *)(int, int, int, int))wil::details::ReportUsageToServiceDirect)(a1, a3, a4, v10);
    if ( result )
    {
      if ( g_wil_details_pfnFeatureLoggingHook )
        return g_wil_details_pfnFeatureLoggingHook(g_wil_details_pfnFeatureLoggingHook, a2, a5, 0, a6, &a7, 0, 0, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1003a210  mov     edi, edi
0x1003a212  push    ebp
0x1003a213  mov     ebp, esp
0x1003a215  push    ecx
0x1003a216  mov     eax, [ebp+arg_10]
0x1003a219  mov     [ebp+var_4], edx
0x1003a21c  push    ebx
0x1003a21d  push    esi
0x1003a21e  push    edi
0x1003a21f  mov     edi, ecx
0x1003a221  test    eax, eax
0x1003a223  jz      loc_1003A2F9
0x1003a229  mov     esi, [ebp+arg_C]
0x1003a22c  cmp     eax, 6; switch 7 cases
0x1003a22f  ja      short def_1003A231; jumptable 1003A231 default case
0x1003a231  jmp     ds:jpt_1003A231[eax*4]; switch jump
0x1003a238  xor     eax, eax; jumptable 1003A231 case 1
0x1003a23a  mov     ecx, 4
0x1003a23f  test    esi, esi
0x1003a241  cmovnz  ecx, eax
0x1003a244  jmp     short loc_1003A2B7
0x1003a246  xor     ecx, ecx; jumptable 1003A231 case 2
0x1003a248  test    esi, esi
0x1003a24a  setz    cl
0x1003a24d  lea     ecx, ds:1[ecx*4]
0x1003a254  jmp     short loc_1003A2B7
0x1003a256  xor     ecx, ecx; jumptable 1003A231 case 3
0x1003a258  test    esi, esi
0x1003a25a  setz    cl
0x1003a25d  lea     ecx, ds:2[ecx*4]
0x1003a264  jmp     short loc_1003A2B7
0x1003a266  xor     ecx, ecx; jumptable 1003A231 case 4
0x1003a268  test    esi, esi
0x1003a26a  setz    cl
0x1003a26d  lea     ecx, ds:3[ecx*4]
0x1003a274  jmp     short loc_1003A2B7
0x1003a276  xor     ecx, ecx; jumptable 1003A231 case 5
0x1003a278  test    esi, esi
0x1003a27a  setz    cl
0x1003a27d  lea     ecx, ds:8[ecx*2]
0x1003a284  jmp     short loc_1003A2B7
0x1003a286  xor     ecx, ecx; jumptable 1003A231 case 6
0x1003a288  test    esi, esi
0x1003a28a  setz    cl
0x1003a28d  lea     ecx, ds:9[ecx*2]
0x1003a294  jmp     short loc_1003A2B7
0x1003a296  sub     al, 64h ; 'd'; jumptable 1003A231 default case
0x1003a298  cmp     al, 31h ; '1'
0x1003a29a  ja      short loc_1003A2B2; jumptable 1003A231 case 0
0x1003a29c  test    esi, esi
0x1003a29e  movzx   eax, al
0x1003a2a1  mov     ecx, 64h ; 'd'
0x1003a2a6  mov     ebx, 96h
0x1003a2ab  cmovz   ecx, ebx
0x1003a2ae  add     ecx, eax
0x1003a2b0  jmp     short loc_1003A2B7
0x1003a2b2  mov     ecx, 0FFh; jumptable 1003A231 case 0
0x1003a2b7  mov     ebx, [ebp+arg_8]
0x1003a2ba  movzx   eax, byte ptr [ebx+4]
0x1003a2be  push    eax
0x1003a2bf  sub     esp, 8
0x1003a2c2  push    ecx
0x1003a2c3  push    [ebp+arg_4]
0x1003a2c6  mov     ecx, edi
0x1003a2c8  push    [ebp+arg_0]
0x1003a2cb  call    ?ReportUsageToServiceDirect@details@wil@@YGHPAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@IKE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,ulong,uchar)
0x1003a2d0  test    eax, eax
0x1003a2d2  jz      short loc_1003A2F9
0x1003a2d4  mov     edi, _g_wil_details_pfnFeatureLoggingHook
0x1003a2da  test    edi, edi
0x1003a2dc  jz      short loc_1003A2F9
0x1003a2de  push    1
0x1003a2e0  push    0
0x1003a2e2  push    0
0x1003a2e4  lea     eax, [ebp+arg_10]
0x1003a2e7  mov     ecx, edi
0x1003a2e9  push    eax
0x1003a2ea  push    esi
0x1003a2eb  push    0
0x1003a2ed  push    ebx; unsigned int
0x1003a2ee  push    [ebp+var_4]; void *
0x1003a2f1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003a2f7  call    edi ; _g_wil_details_pfnFeatureLoggingHook
0x1003a2f9  pop     edi
0x1003a2fa  pop     esi
0x1003a2fb  pop     ebx
0x1003a2fc  mov     esp, ebp
0x1003a2fe  pop     ebp
0x1003a2ff  retn    18h
```
