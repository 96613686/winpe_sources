# _PnpCtxGetCachedNodeBaseKey

- ea: `0x1408efb80`
- end: `0x1408efd04`
- name: `_PnpCtxGetCachedNodeBaseKey`
- size: `388`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140833d2c`
- `0x14086faac`
- `0x140878678`
- `0x1408eeed8`
- `0x1408ef0e0`
- `0x1408f5080`
- `0x1408f5990`
- `0x14090d814`
- `0x140910f08`
- `0x1409ba7b8`
- `0x140adf97c`

## callees

- `0x14083a898`
- `0x140873414`
- `0x1408efb80`
- `0x140a51c90`
- `0x140bb19f0`

## string_xrefs

- `0x140b5659f`: `Services`
- `0x140b56638`: `HardwareConfig`
- `0x140b56620`: `Control\CoDeviceInstallers`

## pseudocode

```c
__int64 __fastcall PnpCtxGetCachedNodeBaseKey(__int64 a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  int v4; // edi
  __int64 result; // rax
  __int64 v8; // r9
  __int64 v9; // rcx
  void *EnumSecurityDescriptor; // r15
  __int64 v11; // r10
  int CachedContextBaseKey; // r14d
  __int64 v13; // rax
  __int64 v14; // [rsp+50h] [rbp-10h] BYREF
  __int64 v15; // [rsp+58h] [rbp-8h] BYREF

  v4 = a3 - 1;
  v14 = 0;
  v15 = 0;
  result = 0;
  v8 = 1;
  if ( (_DWORD)a3 != 5 )
  {
    switch ( (int)a3 )
    {
      case 1:
        result = SysCtxGetCachedContextBaseKey(a2[7], 1, &v14, 1);
        goto LABEL_12;
      case 2:
        result = SysCtxGetCachedContextBaseKey(a2[7], 2, &v14, 1);
        goto LABEL_12;
      case 3:
        result = SysCtxGetCachedContextBaseKey(a2[7], 3, &v14, 1);
        goto LABEL_12;
      case 4:
        if ( *(_QWORD *)(a2[7] + 48LL) )
        {
          result = 0;
          v14 = *(_QWORD *)(a2[7] + 48LL);
        }
        else
        {
          result = 3221225524LL;
        }
LABEL_12:
        if ( (int)result < 0 )
          return result;
        goto LABEL_6;
      case 6:
        v9 = a2[9];
        goto LABEL_5;
      case 7:
        v9 = a2[10];
        goto LABEL_5;
      case 8:
        v9 = a2[11];
        goto LABEL_5;
      case 9:
        v9 = a2[12];
        goto LABEL_5;
      case 10:
        v9 = a2[13];
        goto LABEL_5;
      case 11:
        v9 = a2[14];
        goto LABEL_5;
      case 12:
        v9 = a2[15];
        goto LABEL_5;
      case 13:
        v9 = a2[16];
        goto LABEL_5;
      case 14:
        v9 = a2[17];
        goto LABEL_5;
      case 15:
        v9 = a2[18];
        goto LABEL_5;
      default:
        return 3221225485LL;
    }
  }
  v9 = a2[8];
LABEL_5:
  v14 = v9;
LABEL_6:
  if ( v14 )
  {
    *a4 = v14;
  }
  else
  {
    switch ( v4 )
    {
      case 4:
      case 5:
      case 6:
      case 7:
      case 8:
      case 9:
      case 10:
      case 11:
      case 12:
      case 13:
      case 14:
        EnumSecurityDescriptor = 0;
        switch ( v4 )
        {
          case 0:
          case 1:
          case 2:
          case 3:
            return 3221225485LL;
          case 4:
            EnumSecurityDescriptor = (void *)PnpGetEnumSecurityDescriptor(0, a2, a3, v8);
            if ( EnumSecurityDescriptor )
            {
              v8 = 4;
LABEL_40:
              CachedContextBaseKey = SysCtxGetCachedContextBaseKey(a2[7], (unsigned int)v8, &v15, v8);
              if ( CachedContextBaseKey >= 0 )
              {
                CachedContextBaseKey = SysCtxRegCreateTree(a2[7], v15, v11, 0, 0x2000000, 0);
                if ( CachedContextBaseKey >= 0 )
                {
                  switch ( v4 )
                  {
                    case 0:
                    case 1:
                    case 2:
                    case 3:
                      CachedContextBaseKey = -1073741811;
                      goto LABEL_56;
                    case 4:
                      v13 = v14;
                      a2[8] = v14;
                      break;
                    case 5:
                      v13 = v14;
                      a2[9] = v14;
                      break;
                    case 6:
                      v13 = v14;
                      a2[10] = v14;
                      break;
                    case 7:
                      v13 = v14;
                      a2[11] = v14;
                      break;
                    case 8:
                      v13 = v14;
                      a2[12] = v14;
                      break;
                    case 9:
                      v13 = v14;
                      a2[13] = v14;
                      break;
                    case 10:
                      v13 = v14;
                      a2[14] = v14;
                      break;
                    case 11:
                      v13 = v14;
                      a2[15] = v14;
                      break;
                    case 12:
                      v13 = v14;
                      a2[16] = v14;
                      break;
                    case 13:
                      v13 = v14;
                      a2[17] = v14;
                      break;
                    case 14:
                      v13 = v14;
                      a2[18] = v14;
                      break;
                    default:
                      return 3221225485LL;
                  }
                  *a4 = v13;
                }
              }
LABEL_56:
              if ( EnumSecurityDescriptor )
                ExFreePoolWithTag(EnumSecurityDescriptor, 0);
              result = (unsigned int)CachedContextBaseKey;
            }
            else
            {
              result = 3221225701LL;
            }
            break;
          case 5:
            v8 = 4;
            goto LABEL_40;
          case 6:
            v8 = 4;
            goto LABEL_40;
          case 7:
            v8 = 4;
            goto LABEL_40;
          case 8:
            v8 = 4;
            goto LABEL_40;
          case 9:
            v8 = 4;
            goto LABEL_40;
          case 10:
            v8 = 4;
            goto LABEL_40;
          case 11:
            v8 = 4;
            goto LABEL_40;
          case 12:
            v8 = 4;
            goto LABEL_40;
          case 13:
            v8 = 4;
            goto LABEL_40;
          case 14:
            goto LABEL_40;
          default:
            return 3221225485LL;
        }
        break;
      default:
        return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1408efb80  mov     [rsp-28h+arg_8], rbx
0x1408efb85  mov     [rsp-28h+arg_10], rsi
0x1408efb8a  push    rbp
0x1408efb8b  push    rdi
0x1408efb8c  push    r12
0x1408efb8e  push    r13
0x1408efb90  push    r14
0x1408efb92  mov     rbp, rsp
0x1408efb95  sub     rsp, 60h
0x1408efb99  xor     r12d, r12d
0x1408efb9c  lea     edi, [r8-1]; switch 15 cases
0x1408efba0  mov     [rbp+var_10], r12
0x1408efba4  mov     rbx, r9
0x1408efba7  mov     [rbp+var_8], r12
0x1408efbab  mov     rsi, rdx
0x1408efbae  lea     r13, cs:140000000h
0x1408efbb5  mov     r10, rcx
0x1408efbb8  mov     eax, r12d
0x1408efbbb  mov     r9d, 1
0x1408efbc1  cmp     r8d, 5
0x1408efbc5  jz      short loc_1408EFBE6
0x1408efbc7  cmp     edi, 0Eh
0x1408efbca  ja      short def_1408EFBDA; jumptable 00000001408EFBDA default case, case 5
0x1408efbcc  movsxd  rcx, edi
0x1408efbcf  mov     edx, ds:(jpt_1408EFBDA - 140000000h)[r13+rcx*4]
0x1408efbd7  add     rdx, r13
0x1408efbda  jmp     rdx; switch jump
0x1408efbe0  mov     rcx, [rsi+60h]; jumptable 00000001408EFBDA case 9
0x1408efbe4  jmp     short loc_1408EFBEA
0x1408efbe6  mov     rcx, [rdx+40h]
0x1408efbea  mov     [rbp+var_10], rcx
0x1408efbee  mov     rcx, [rbp+var_10]
0x1408efbf2  test    rcx, rcx
0x1408efbf5  jz      loc_140B56534
0x1408efbfb  mov     [rbx], rcx
0x1408efbfe  lea     r11, [rsp+60h+var_s0]
0x1408efc03  mov     rbx, [r11+38h]
0x1408efc07  mov     rsi, [r11+40h]
0x1408efc0b  mov     rsp, r11
0x1408efc0e  pop     r14
0x1408efc10  pop     r13
0x1408efc12  pop     r12
0x1408efc14  pop     rdi
0x1408efc15  pop     rbp
0x1408efc16  retn
0x1408efc18  mov     eax, 0C000000Dh; jumptable 00000001408EFBDA default case, case 5
0x1408efc1d  jmp     short loc_1408EFBFE
0x1408efc1f  mov     rcx, [rsi+58h]; jumptable 00000001408EFBDA case 8
0x1408efc23  jmp     short loc_1408EFBEA
0x1408efc25  mov     rax, [rsi+38h]; jumptable 00000001408EFBDA case 4
0x1408efc29  mov     rcx, [rax+30h]
0x1408efc2d  test    rcx, rcx
0x1408efc30  jz      short loc_1408EFC51
0x1408efc32  mov     eax, r12d
0x1408efc35  mov     [rbp+var_10], rcx
0x1408efc39  test    eax, eax
0x1408efc3b  jns     short loc_1408EFBEE
0x1408efc3d  jmp     short loc_1408EFBFE
0x1408efc3f  mov     rcx, [rsi+50h]; jumptable 00000001408EFBDA case 7
0x1408efc43  jmp     short loc_1408EFBEA
0x1408efc45  mov     rcx, [rsi+48h]; jumptable 00000001408EFBDA case 6
0x1408efc49  jmp     short loc_1408EFBEA
0x1408efc4b  mov     rcx, [rsi+68h]; jumptable 00000001408EFBDA case 10
0x1408efc4f  jmp     short loc_1408EFBEA
0x1408efc51  mov     eax, 0C0000034h
0x1408efc56  jmp     short loc_1408EFC39
0x1408efc58  mov     rcx, [rsi+88h]; jumptable 00000001408EFBDA case 14
0x1408efc5f  jmp     short loc_1408EFBEA
0x1408efc61  mov     rcx, [rsi+70h]; jumptable 00000001408EFBDA case 11
0x1408efc65  jmp     short loc_1408EFBEA
0x1408efc67  mov     rcx, [rsi+78h]; jumptable 00000001408EFBDA case 12
0x1408efc6b  jmp     loc_1408EFBEA
0x1408efc70  mov     rcx, [rsi+80h]; jumptable 00000001408EFBDA case 13
0x1408efc77  jmp     loc_1408EFBEA
0x1408efc7c  mov     rcx, [rsi+90h]; jumptable 00000001408EFBDA case 15
0x1408efc83  jmp     loc_1408EFBEA
0x1408efc88  mov     rcx, [rsi+38h]; jumptable 00000001408EFBDA case 1
0x1408efc8c  lea     r8, [rbp+var_10]
0x1408efc90  mov     edx, r9d
0x1408efc93  call    _SysCtxGetCachedContextBaseKey
0x1408efc98  jmp     short loc_1408EFC39
0x1408efc9a  mov     rcx, [rsi+38h]; jumptable 00000001408EFBDA case 2
0x1408efc9e  lea     r8, [rbp+var_10]
0x1408efca2  mov     edx, 2
0x1408efca7  call    _SysCtxGetCachedContextBaseKey
0x1408efcac  jmp     short loc_1408EFC39
0x1408efcae  mov     rcx, [rsi+38h]; jumptable 00000001408EFBDA case 3
0x1408efcb2  lea     r8, [rbp+var_10]
0x1408efcb6  mov     edx, 3
0x1408efcbb  call    _SysCtxGetCachedContextBaseKey
0x1408efcc0  jmp     loc_1408EFC39
0x140b56534  cmp     edi, 0Eh; switch 15 cases
0x140b56537  ja      def_1408EFBDA; jumptable 00000001408EFBDA default case, case 5
0x140b5653d  movsxd  rax, edi
0x140b56540  mov     ecx, ds:(jpt_140B5654B - 140000000h)[r13+rax*4]
0x140b56548  add     rcx, r13
0x140b5654b  jmp     rcx; switch jump
0x140b56551  mov     [rsp+60h+arg_0], r15; jumptable 0000000140B5654B cases 4-14
0x140b56559  mov     r15, r12
0x140b5655c  movsxd  rax, edi
0x140b5655f  mov     ecx, ds:(jpt_140B5656A - 140000000h)[r13+rax*4]
0x140b56567  add     rcx, r13
0x140b5656a  jmp     rcx; switch jump
0x140b56570  call    _PnpGetEnumSecurityDescriptor; jumptable 0000000140B5656A case 4
0x140b56575  mov     r15, rax
0x140b56578  test    rax, rax
0x140b5657b  jnz     short loc_140B56587
0x140b5657d  mov     eax, 0C00000E5h
0x140b56582  jmp     loc_140B56740
0x140b56587  mov     r9d, 4
0x140b5658d  lea     r10, aEnum; "Enum"
0x140b56594  jmp     loc_140B5663F
0x140b56599  mov     r9d, 4; jumptable 0000000140B5656A case 5
0x140b5659f  lea     r10, aServices_2; "Services"
0x140b565a6  jmp     loc_140B5663F
0x140b565ab  mov     r9d, 4; jumptable 0000000140B5656A case 6
0x140b565b1  lea     r10, aControlClass_0; "Control\\Class"
0x140b565b8  jmp     loc_140B5663F
0x140b565bd  mov     r9d, 4; jumptable 0000000140B5656A case 7
0x140b565c3  lea     r10, aControlDevicec_2; "Control\\DeviceClasses"
0x140b565ca  jmp     short loc_140B5663F
0x140b565cc  movzx   ecx, byte ptr [r10+4]; jumptable 0000000140B5656A case 8
0x140b565d1  lea     rax, aControlDevicec_2; "Control\\DeviceClasses"
0x140b565d8  test    cl, cl
0x140b565da  lea     r10, aControlDevicei; "Control\\DeviceInterfaces"
0x140b565e1  mov     r9d, 4
0x140b565e7  cmovz   r10, rax
0x140b565eb  jmp     short loc_140B5663F
0x140b565ed  mov     r9d, 4; jumptable 0000000140B5656A case 9
0x140b565f3  lea     r10, aControlDevicec; "Control\\DeviceContainers"
0x140b565fa  jmp     short loc_140B5663F
0x140b565fc  mov     r9d, 4; jumptable 0000000140B5656A case 10
0x140b56602  lea     r10, aControlDevicep; "Control\\DevicePanels"
0x140b56609  jmp     short loc_140B5663F
0x140b5660b  mov     r9d, 4; jumptable 0000000140B5656A case 11
0x140b56611  lea     r10, aControlCritica; "Control\\CriticalDeviceDatabase"
0x140b56618  jmp     short loc_140B5663F
0x140b5661a  mov     r9d, 4; jumptable 0000000140B5656A case 12
0x140b56620  lea     r10, aControlCodevic; "Control\\CoDeviceInstallers"
0x140b56627  jmp     short loc_140B5663F
0x140b56629  mov     r9d, 4; jumptable 0000000140B5656A case 13
0x140b5662f  lea     r10, aHardwareProfil_2; "Hardware Profiles"
0x140b56636  jmp     short loc_140B5663F
0x140b56638  lea     r10, aHardwareconfig_0; jumptable 0000000140B5656A case 14
0x140b5663f  mov     rcx, [rsi+38h]
0x140b56643  lea     r8, [rbp+var_8]
0x140b56647  mov     edx, r9d
0x140b5664a  call    _SysCtxGetCachedContextBaseKey
0x140b5664f  mov     r14d, eax
0x140b56652  test    eax, eax
0x140b56654  js      loc_140B56727
0x140b5665a  mov     rdx, [rbp+var_8]
0x140b5665e  lea     rax, [rbp+var_10]
0x140b56662  mov     rcx, [rsi+38h]
0x140b56666  xor     r9d, r9d
0x140b56669  mov     [rsp+60h+var_20], r12
0x140b5666e  mov     r8, r10
0x140b56671  mov     [rsp+60h+var_28], rax
0x140b56676  mov     [rsp+60h+var_38], r12
0x140b5667b  mov     [rsp+60h+var_40], 2000000h
0x140b56683  call    _SysCtxRegCreateTree
0x140b56688  mov     r14d, eax
0x140b5668b  test    eax, eax
0x140b5668d  js      loc_140B56727
0x140b56693  movsxd  rax, edi
0x140b56696  mov     ecx, ds:(jpt_140B566A1 - 140000000h)[r13+rax*4]; switch 15 cases
0x140b5669e  add     rcx, r13
0x140b566a1  jmp     rcx; switch jump
0x140b566a7  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 4
0x140b566ab  mov     [rsi+40h], rax
0x140b566af  jmp     short loc_140B5671C
0x140b566b1  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 5
0x140b566b5  mov     [rsi+48h], rax
0x140b566b9  jmp     short loc_140B5671C
0x140b566bb  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 6
0x140b566bf  mov     [rsi+50h], rax
0x140b566c3  jmp     short loc_140B5671C
0x140b566c5  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 7
0x140b566c9  mov     [rsi+58h], rax
0x140b566cd  jmp     short loc_140B5671C
0x140b566cf  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 8
0x140b566d3  mov     [rsi+60h], rax
0x140b566d7  jmp     short loc_140B5671C
0x140b566d9  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 9
0x140b566dd  mov     [rsi+68h], rax
0x140b566e1  jmp     short loc_140B5671C
0x140b566e3  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 10
0x140b566e7  mov     [rsi+70h], rax
0x140b566eb  jmp     short loc_140B5671C
0x140b566ed  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 11
0x140b566f1  mov     [rsi+78h], rax
0x140b566f5  jmp     short loc_140B5671C
0x140b566f7  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 12
0x140b566fb  mov     [rsi+80h], rax
0x140b56702  jmp     short loc_140B5671C
0x140b56704  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 13
0x140b56708  mov     [rsi+88h], rax
0x140b5670f  jmp     short loc_140B5671C
0x140b56711  mov     rax, [rbp+var_10]; jumptable 0000000140B566A1 case 14
0x140b56715  mov     [rsi+90h], rax
0x140b5671c  mov     [rbx], rax
0x140b5671f  jmp     short loc_140B56727
0x140b56721  mov     r14d, 0C000000Dh; jumptable 0000000140B566A1 cases 0-3
0x140b56727  test    r15, r15
0x140b5672a  jz      short loc_140B56736
0x140b5672c  xor     edx, edx; Tag
0x140b5672e  mov     rcx, r15; P
0x140b56731  call    ExFreePoolWithTag
0x140b56736  mov     eax, r14d
0x140b56739  jmp     short loc_140B56740
0x140b5673b  mov     eax, 0C000000Dh; jumptable 0000000140B5656A cases 0-3
0x140b56740  mov     r15, [rsp+60h+arg_0]
0x140b56748  jmp     loc_1408EFBFE
```
