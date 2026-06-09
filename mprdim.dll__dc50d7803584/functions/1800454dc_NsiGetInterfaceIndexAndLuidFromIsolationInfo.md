# NsiGetInterfaceIndexAndLuidFromIsolationInfo

- ea: `0x1800454dc`
- end: `0x18004568d`
- name: `NsiGetInterfaceIndexAndLuidFromIsolationInfo`
- size: `433`
- prototype: `__int64 __fastcall(int, int, int, int, PNET_IFINDEX InterfaceIndex)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005d14`
- `0x180015490`

## callees

- `0x180045430`
- `0x1800454dc`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180045577`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180045668`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180045577`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180045668`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180045638`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180045638`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180045567`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180045567`
- `NSI!NsiFreeTable` at `0x18004565a`
- `NSI!NsiFreeTable` at `0x18004565a`
- `NSI!NsiAllocateAndGetTable` at `0x1800455e0`
- `NSI!NsiAllocateAndGetTable` at `0x1800455e0`

## pseudocode

```c
__int64 __fastcall NsiGetInterfaceIndexAndLuidFromIsolationInfo(
        __int64 a1,
        __int64 a2,
        int a3,
        ULONG64 *a4,
        PNET_IFINDEX InterfaceIndex)
{
  int v6; // r13d
  NET_IF_COMPARTMENT_ID v7; // r14d
  unsigned int CompartmentIdForRoutingDomain; // edi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // eax
  NET_IF_COMPARTMENT_ID v11; // r12d
  __int64 i; // rdx
  __int64 v13; // rax
  const NET_LUID *v14; // rcx
  ULONG *v15; // rdx
  unsigned int v17; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+80h] [rbp+17h] BYREF
  __int64 v19; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v20; // [rsp+90h] [rbp+27h] BYREF
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+D0h] [rbp+67h] BYREF
  int v22; // [rsp+D8h] [rbp+6Fh]

  v22 = a3;
  v18 = 0;
  v20 = 0;
  v6 = 0;
  CompartmentId = 1;
  v19 = 0;
  v7 = 1;
  v17 = 0;
  if ( a2 && a4 && InterfaceIndex )
  {
    CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain(a2, &CompartmentId);
    if ( !CompartmentIdForRoutingDomain )
    {
      CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
      v11 = CompartmentId;
      v7 = CurrentThreadCompartmentId;
      CompartmentIdForRoutingDomain = SetCurrentThreadCompartmentId(CompartmentId);
      if ( !CompartmentIdForRoutingDomain )
      {
        v6 = 1;
        CompartmentIdForRoutingDomain = NsiAllocateAndGetTable(
                                          1,
                                          &NPI_MS_IPV4_MODULEID,
                                          7,
                                          &v18,
                                          8,
                                          0,
                                          0,
                                          &v20,
                                          88,
                                          &v19,
                                          32,
                                          &v17,
                                          0);
        if ( !CompartmentIdForRoutingDomain )
        {
          for ( i = 0; (unsigned int)i < v17; i = (unsigned int)(i + 1) )
          {
            if ( *(_DWORD *)(88LL * (unsigned int)i + v20 + 4) == v11 )
            {
              v13 = 32LL * (unsigned int)i;
              if ( *(_DWORD *)(v13 + v19 + 24) == v22 && *(_QWORD *)(v13 + v19 + 16) == a1 )
              {
                v14 = (const NET_LUID *)(v18 + 8 * i);
                v15 = InterfaceIndex;
                *a4 = v14->Value;
                CompartmentIdForRoutingDomain = ConvertInterfaceLuidToIndex(v14, v15);
                break;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    CompartmentIdForRoutingDomain = 87;
  }
  if ( v18 )
    NsiFreeTable(v18, 0, v20, v19);
  if ( v6 )
    SetCurrentThreadCompartmentId(v7);
  return CompartmentIdForRoutingDomain;
}

```

## disassembly

```asm
0x1800454dc  mov     rax, rsp
0x1800454df  mov     [rax+8], rbx
0x1800454e3  mov     [rax+20h], rdi
0x1800454e7  mov     [rax+18h], r8d
0x1800454eb  push    rbp
0x1800454ec  push    r12
0x1800454ee  push    r13
0x1800454f0  push    r14
0x1800454f2  push    r15
0x1800454f4  lea     rbp, [rax-57h]
0x1800454f8  sub     rsp, 90h
0x1800454ff  mov     rbx, rcx
0x180045502  mov     [rbp+4Fh+var_38], 0
0x18004550a  mov     ecx, 1
0x18004550f  mov     [rbp+4Fh+var_28], 0
0x180045517  xor     r13d, r13d
0x18004551a  mov     [rbp+4Fh+CompartmentId], ecx
0x18004551d  mov     [rbp+4Fh+var_30], 0
0x180045525  mov     r14d, ecx
0x180045528  mov     [rbp+4Fh+var_40], 0
0x18004552f  mov     r15, r9
0x180045532  mov     rax, rdx
0x180045535  test    rdx, rdx
0x180045538  jz      loc_180045642
0x18004553e  test    r9, r9
0x180045541  jz      loc_180045642
0x180045547  cmp     [rbp+4Fh+InterfaceIndex], r13
0x18004554b  jz      loc_180045642
0x180045551  lea     rdx, [rbp+4Fh+CompartmentId]
0x180045555  mov     rcx, rax
0x180045558  call    NsiGetCompartmentIdForRoutingDomain
0x18004555d  mov     edi, eax
0x18004555f  test    eax, eax
0x180045561  jnz     loc_180045647
0x180045567  call    cs:__imp_GetCurrentThreadCompartmentId
0x18004556d  mov     r12d, [rbp+4Fh+CompartmentId]
0x180045571  mov     ecx, r12d; CompartmentId
0x180045574  mov     r14d, eax
0x180045577  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004557d  mov     edi, eax
0x18004557f  test    eax, eax
0x180045581  jnz     loc_180045647
0x180045587  mov     [rsp+0B0h+var_50], al
0x18004558b  lea     ecx, [rax+1]
0x18004558e  lea     rax, [rbp+4Fh+var_40]
0x180045592  mov     r13d, ecx
0x180045595  mov     qword ptr [rsp+0B0h+var_58], rax
0x18004559a  lea     r9, [rbp+4Fh+var_38]
0x18004559e  mov     dword ptr [rsp+0B0h+var_60], 20h ; ' '
0x1800455a6  lea     rax, [rbp+4Fh+var_30]
0x1800455aa  mov     qword ptr [rsp+0B0h+var_68], rax
0x1800455af  lea     r8d, [rdi+7]
0x1800455b3  mov     dword ptr [rsp+0B0h+var_70], 58h ; 'X'
0x1800455bb  lea     rax, [rbp+4Fh+var_28]
0x1800455bf  mov     qword ptr [rsp+0B0h+var_78], rax
0x1800455c4  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800455cb  mov     dword ptr [rsp+0B0h+var_80], edi
0x1800455cf  mov     qword ptr [rsp+0B0h+var_88], 0
0x1800455d8  mov     dword ptr [rsp+0B0h+var_90], 8
0x1800455e0  call    cs:__imp_NsiAllocateAndGetTable
0x1800455e6  mov     edi, eax
0x1800455e8  test    eax, eax
0x1800455ea  jnz     short loc_180045647
0x1800455ec  mov     r9d, [rbp+4Fh+arg_10]
0x1800455f0  xor     edx, edx
0x1800455f2  cmp     edx, [rbp+4Fh+var_40]
0x1800455f5  jnb     short loc_180045647
0x1800455f7  mov     rax, [rbp+4Fh+var_28]
0x1800455fb  mov     r8d, edx
0x1800455fe  imul    rcx, r8, 58h ; 'X'
0x180045602  cmp     [rcx+rax+4], r12d
0x180045607  jnz     short loc_180045622
0x180045609  mov     rcx, [rbp+4Fh+var_30]
0x18004560d  mov     eax, r8d
0x180045610  shl     rax, 5
0x180045614  cmp     [rax+rcx+18h], r9d
0x180045619  jnz     short loc_180045622
0x18004561b  cmp     [rax+rcx+10h], rbx
0x180045620  jz      short loc_180045626
0x180045622  inc     edx
0x180045624  jmp     short loc_1800455F2
0x180045626  mov     rax, [rbp+4Fh+var_38]
0x18004562a  lea     rcx, [rax+rdx*8]; InterfaceLuid
0x18004562e  mov     rdx, [rbp+4Fh+InterfaceIndex]; InterfaceIndex
0x180045632  mov     rax, [rcx]
0x180045635  mov     [r15], rax
0x180045638  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18004563e  mov     edi, eax
0x180045640  jmp     short loc_180045647
0x180045642  mov     edi, 57h ; 'W'
0x180045647  mov     rcx, [rbp+4Fh+var_38]
0x18004564b  test    rcx, rcx
0x18004564e  jz      short loc_180045660
0x180045650  mov     r9, [rbp+4Fh+var_30]
0x180045654  xor     edx, edx
0x180045656  mov     r8, [rbp+4Fh+var_28]
0x18004565a  call    cs:__imp_NsiFreeTable
0x180045660  test    r13d, r13d
0x180045663  jz      short loc_18004566E
0x180045665  mov     ecx, r14d; CompartmentId
0x180045668  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004566e  lea     r11, [rsp+0B0h+var_20]
0x180045676  mov     eax, edi
0x180045678  mov     rbx, [r11+30h]
0x18004567c  mov     rdi, [r11+48h]
0x180045680  mov     rsp, r11
0x180045683  pop     r15
0x180045685  pop     r14
0x180045687  pop     r13
0x180045689  pop     r12
0x18004568b  pop     rbp
0x18004568c  retn
```
