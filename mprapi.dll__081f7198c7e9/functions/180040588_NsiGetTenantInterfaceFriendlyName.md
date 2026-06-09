# NsiGetTenantInterfaceFriendlyName

- ea: `0x180040588`
- end: `0x180040737`
- name: `NsiGetTenantInterfaceFriendlyName`
- size: `431`
- prototype: `__int64 __fastcall(int, int, int, int, PWSTR InterfaceAlias)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022324`

## callees

- `0x180040424`
- `0x180040588`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180040617`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180040712`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180040617`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180040712`
- `IPHLPAPI!ConvertInterfaceLuidToAlias` at `0x1800406e2`
- `IPHLPAPI!ConvertInterfaceLuidToAlias` at `0x1800406e2`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180040607`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180040607`
- `NSI!NsiAllocateAndGetTable` at `0x180040680`
- `NSI!NsiAllocateAndGetTable` at `0x180040680`
- `NSI!NsiFreeTable` at `0x180040704`
- `NSI!NsiFreeTable` at `0x180040704`

## pseudocode

```c
__int64 __fastcall NsiGetTenantInterfaceFriendlyName(int a1, __int64 a2, __int64 a3, __int64 a4, PWSTR InterfaceAlias)
{
  int v5; // r12d
  NET_IF_COMPARTMENT_ID v8; // r14d
  unsigned int CompartmentIdForRoutingDomain; // edi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // eax
  NET_IF_COMPARTMENT_ID v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v15; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v16; // [rsp+80h] [rbp+17h] BYREF
  __int64 v17; // [rsp+88h] [rbp+1Fh] BYREF
  unsigned int v18; // [rsp+D8h] [rbp+6Fh] BYREF
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+E0h] [rbp+77h] BYREF

  v15 = 0;
  v5 = 0;
  CompartmentId = 1;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v8 = 1;
  if ( a3 && InterfaceAlias )
  {
    CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain(a3, &CompartmentId);
    if ( !CompartmentIdForRoutingDomain )
    {
      CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
      v11 = CompartmentId;
      v8 = CurrentThreadCompartmentId;
      CompartmentIdForRoutingDomain = SetCurrentThreadCompartmentId(CompartmentId);
      if ( !CompartmentIdForRoutingDomain )
      {
        v5 = 1;
        CompartmentIdForRoutingDomain = NsiAllocateAndGetTable(
                                          1,
                                          &NPI_MS_IPV4_MODULEID,
                                          7,
                                          &v15,
                                          8,
                                          0,
                                          0,
                                          &v17,
                                          88,
                                          &v16,
                                          32,
                                          &v18,
                                          0);
        if ( !CompartmentIdForRoutingDomain )
        {
          v12 = 0;
          if ( v18 )
          {
            while ( 1 )
            {
              if ( *(_DWORD *)(88LL * (unsigned int)v12 + v17 + 4) == v11 )
              {
                v13 = 32LL * (unsigned int)v12;
                if ( *(_DWORD *)(v13 + v16 + 24) == a1 && *(_QWORD *)(v13 + v16 + 16) == a2 )
                  break;
              }
              v12 = (unsigned int)(v12 + 1);
              if ( (unsigned int)v12 >= v18 )
                goto LABEL_11;
            }
            CompartmentIdForRoutingDomain = ConvertInterfaceLuidToAlias(
                                              (const NET_LUID *)(v15 + 8 * v12),
                                              InterfaceAlias,
                                              0x100u);
          }
          else
          {
LABEL_11:
            CompartmentIdForRoutingDomain = 2;
          }
        }
      }
    }
  }
  else
  {
    CompartmentIdForRoutingDomain = 87;
  }
  if ( v15 )
    NsiFreeTable(v15, 0, v17, v16);
  if ( v5 )
    SetCurrentThreadCompartmentId(v8);
  return CompartmentIdForRoutingDomain;
}

```

## disassembly

```asm
0x180040588  mov     rax, rsp
0x18004058b  mov     [rax+8], rbx
0x18004058f  mov     [rax+10h], rdi
0x180040593  mov     [rax+20h], r9d
0x180040597  push    rbp
0x180040598  push    r12
0x18004059a  push    r13
0x18004059c  push    r14
0x18004059e  push    r15
0x1800405a0  lea     rbp, [rax-57h]
0x1800405a4  sub     rsp, 90h
0x1800405ab  mov     eax, 1
0x1800405b0  mov     [rbp+4Fh+var_40], 0
0x1800405b8  xor     r12d, r12d
0x1800405bb  mov     [rbp+4Fh+CompartmentId], eax
0x1800405be  mov     [rbp+4Fh+var_30], 0
0x1800405c6  mov     rbx, rdx
0x1800405c9  mov     [rbp+4Fh+var_38], 0
0x1800405d1  mov     r13d, ecx
0x1800405d4  mov     [rbp+4Fh+arg_10], 0
0x1800405db  mov     r14d, eax
0x1800405de  test    r8, r8
0x1800405e1  jz      loc_1800406EC
0x1800405e7  cmp     [rbp+4Fh+InterfaceAlias], r12
0x1800405eb  jz      loc_1800406EC
0x1800405f1  lea     rdx, [rbp+4Fh+CompartmentId]
0x1800405f5  mov     rcx, r8
0x1800405f8  call    NsiGetCompartmentIdForRoutingDomain
0x1800405fd  mov     edi, eax
0x1800405ff  test    eax, eax
0x180040601  jnz     loc_1800406F1
0x180040607  call    cs:__imp_GetCurrentThreadCompartmentId
0x18004060d  mov     r15d, [rbp+4Fh+CompartmentId]
0x180040611  mov     ecx, r15d; CompartmentId
0x180040614  mov     r14d, eax
0x180040617  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004061d  mov     edi, eax
0x18004061f  test    eax, eax
0x180040621  jnz     loc_1800406F1
0x180040627  mov     [rsp+0B0h+var_50], al
0x18004062b  lea     ecx, [rax+1]
0x18004062e  lea     rax, [rbp+4Fh+arg_10]
0x180040632  mov     r12d, ecx
0x180040635  mov     qword ptr [rsp+0B0h+var_58], rax
0x18004063a  lea     r9, [rbp+4Fh+var_40]
0x18004063e  mov     dword ptr [rsp+0B0h+var_60], 20h ; ' '
0x180040646  lea     rax, [rbp+4Fh+var_38]
0x18004064a  mov     qword ptr [rsp+0B0h+var_68], rax
0x18004064f  lea     r8d, [rdi+7]
0x180040653  mov     dword ptr [rsp+0B0h+var_70], 58h ; 'X'
0x18004065b  lea     rax, [rbp+4Fh+var_30]
0x18004065f  mov     qword ptr [rsp+0B0h+var_78], rax
0x180040664  lea     rdx, NPI_MS_IPV4_MODULEID
0x18004066b  mov     dword ptr [rsp+0B0h+var_80], edi
0x18004066f  mov     qword ptr [rsp+0B0h+var_88], 0
0x180040678  mov     dword ptr [rsp+0B0h+var_90], 8
0x180040680  call    cs:__imp_NsiAllocateAndGetTable
0x180040686  mov     edi, eax
0x180040688  test    eax, eax
0x18004068a  jnz     short loc_1800406F1
0x18004068c  mov     r9d, [rbp+4Fh+arg_10]
0x180040690  xor     edx, edx
0x180040692  test    r9d, r9d
0x180040695  jz      short loc_1800406C9
0x180040697  mov     rax, [rbp+4Fh+var_30]
0x18004069b  mov     r8d, edx
0x18004069e  imul    rcx, r8, 58h ; 'X'
0x1800406a2  cmp     [rcx+rax+4], r15d
0x1800406a7  jnz     short loc_1800406C2
0x1800406a9  mov     rcx, [rbp+4Fh+var_38]
0x1800406ad  mov     eax, r8d
0x1800406b0  shl     rax, 5
0x1800406b4  cmp     [rax+rcx+18h], r13d
0x1800406b9  jnz     short loc_1800406C2
0x1800406bb  cmp     [rax+rcx+10h], rbx
0x1800406c0  jz      short loc_1800406D0
0x1800406c2  inc     edx
0x1800406c4  cmp     edx, r9d
0x1800406c7  jb      short loc_180040697
0x1800406c9  mov     edi, 2
0x1800406ce  jmp     short loc_1800406F1
0x1800406d0  mov     rax, [rbp+4Fh+var_40]
0x1800406d4  mov     r8d, 100h; Length
0x1800406da  lea     rcx, [rax+rdx*8]; InterfaceLuid
0x1800406de  mov     rdx, [rbp+4Fh+InterfaceAlias]; InterfaceAlias
0x1800406e2  call    cs:__imp_ConvertInterfaceLuidToAlias
0x1800406e8  mov     edi, eax
0x1800406ea  jmp     short loc_1800406F1
0x1800406ec  mov     edi, 57h ; 'W'
0x1800406f1  mov     rcx, [rbp+4Fh+var_40]
0x1800406f5  test    rcx, rcx
0x1800406f8  jz      short loc_18004070A
0x1800406fa  mov     r9, [rbp+4Fh+var_38]
0x1800406fe  xor     edx, edx
0x180040700  mov     r8, [rbp+4Fh+var_30]
0x180040704  call    cs:__imp_NsiFreeTable
0x18004070a  test    r12d, r12d
0x18004070d  jz      short loc_180040718
0x18004070f  mov     ecx, r14d; CompartmentId
0x180040712  call    cs:__imp_SetCurrentThreadCompartmentId
0x180040718  lea     r11, [rsp+0B0h+var_20]
0x180040720  mov     eax, edi
0x180040722  mov     rbx, [r11+30h]
0x180040726  mov     rdi, [r11+38h]
0x18004072a  mov     rsp, r11
0x18004072d  pop     r15
0x18004072f  pop     r14
0x180040731  pop     r13
0x180040733  pop     r12
0x180040735  pop     rbp
0x180040736  retn
```
