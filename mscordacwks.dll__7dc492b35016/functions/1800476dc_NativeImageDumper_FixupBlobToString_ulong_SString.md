# NativeImageDumper::FixupBlobToString(ulong,SString &)

- ea: `0x1800476dc`
- end: `0x180048705`
- name: `?FixupBlobToString@NativeImageDumper@@QEAAXKAEAVSString@@@Z`
- size: `4137`
- prototype: `void __fastcall(NativeImageDumper *__hidden this, unsigned int, struct SString *)`
- caller_count: `5`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046cc4`
- `0x180047434`
- `0x180048708`
- `0x180050eec`
- `0x1800544a8`

## callees

- `0x1800210f0`
- `0x180040ef0`
- `0x180040f74`
- `0x180042544`
- `0x180042724`
- `0x180045fa8`
- `0x1800476dc`
- `0x180048a2c`
- `0x180048fb0`
- `0x1800491d8`
- `0x180049c40`
- `0x1800732b8`
- `0x1800737b8`
- `0x180074024`
- `0x180074108`
- `0x180074530`
- `0x180076604`
- `0x1800777d0`
- `0x18009ca04`
- `0x1800c5bd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800485e5`
- `KERNEL32!HeapFree` at `0x180048638`
- `KERNEL32!HeapFree` at `0x180048675`
- `KERNEL32!HeapFree` at `0x1800485e5`
- `KERNEL32!HeapFree` at `0x180048638`
- `KERNEL32!HeapFree` at `0x180048675`
- `KERNEL32!GetProcessHeap` at `0x1800485d0`
- `KERNEL32!GetProcessHeap` at `0x180048623`
- `KERNEL32!GetProcessHeap` at `0x180048660`
- `KERNEL32!GetProcessHeap` at `0x1800485d0`
- `KERNEL32!GetProcessHeap` at `0x180048623`
- `KERNEL32!GetProcessHeap` at `0x180048660`

## string_xrefs

- `0x180047aa9`: `<unresolved token %d>`
- `0x180047f49`: `<unresolved token %d>`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall NativeImageDumper::FixupBlobToString(NativeImageDumper *this, __int64 a2, struct SString *a3)
{
  unsigned __int64 RvaData; // rax
  unsigned __int8 v6; // r15
  struct IMetaDataImport2 *v7; // r14
  char *v8; // rax
  unsigned __int64 v9; // rcx
  int v10; // ebx
  bool v11; // zf
  unsigned __int64 v12; // rcx
  int v13; // ebx
  int v14; // ebx
  unsigned __int64 v15; // rcx
  int v16; // ebx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned __int64 *v19; // rax
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rbx
  unsigned __int16 *v22; // rax
  unsigned int v23; // eax
  unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rdx
  unsigned __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // edx
  const unsigned __int16 *v29; // rdx
  unsigned __int64 v30; // rcx
  int v31; // eax
  unsigned __int64 v32; // rcx
  int v33; // eax
  unsigned int v34; // eax
  struct IMetaDataImport2 *v35; // r9
  unsigned int v36; // edx
  unsigned __int64 v37; // rcx
  unsigned int v38; // eax
  const unsigned __int16 *v39; // rdx
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // rdx
  char *v42; // rax
  unsigned __int64 v43; // rcx
  char v44; // bl
  unsigned __int64 v45; // rcx
  int v46; // ebx
  int v47; // ebx
  unsigned __int64 v48; // rcx
  int v49; // ebx
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rcx
  char *v52; // rax
  unsigned __int64 v53; // rcx
  unsigned int v54; // eax
  unsigned __int64 v55; // rcx
  int v56; // r15d
  unsigned __int64 v57; // rcx
  int v58; // eax
  unsigned __int64 *v59; // r14
  _WORD *v60; // rax
  _WORD *v61; // rbx
  unsigned int v62; // eax
  int v63; // ebx
  unsigned __int64 v64; // rcx
  int v65; // eax
  char *v66; // rax
  unsigned __int64 v67; // rcx
  unsigned int v68; // r15d
  unsigned __int64 v69; // rcx
  int v70; // r15d
  int v71; // r15d
  unsigned __int64 v72; // rcx
  int v73; // r15d
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rcx
  char *v76; // rax
  unsigned __int64 v77; // rcx
  unsigned int v78; // ebx
  unsigned __int64 v79; // rcx
  int v80; // ebx
  int v81; // ebx
  unsigned __int64 v82; // rcx
  int v83; // ebx
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rcx
  int v86; // r12d
  unsigned __int64 v87; // rcx
  int v88; // r12d
  int v89; // r12d
  unsigned __int64 v90; // rcx
  int v91; // r12d
  unsigned __int64 v92; // rcx
  unsigned __int64 v93; // rcx
  unsigned int v94; // r13d
  struct IMetaDataImport2 *v95; // r12
  char *v96; // rax
  unsigned __int64 v97; // rcx
  unsigned int v98; // ebx
  unsigned __int64 v99; // rcx
  int v100; // ebx
  int v101; // ebx
  unsigned __int64 v102; // rcx
  int v103; // ebx
  unsigned __int64 v104; // rcx
  unsigned __int64 v105; // rcx
  unsigned int v106; // eax
  __int64 v107; // rax
  int v108; // eax
  __int64 v109; // rdx
  int v110; // eax
  int MDInternalInterfaceFromPublic; // eax
  int v112; // eax
  const char *v113; // r8
  const char *v114; // rax
  void *v115; // rbx
  HANDLE ProcessHeap; // rax
  void *v117; // rbx
  HANDLE v118; // rax
  void *v119; // rbx
  HANDLE v120; // rax
  unsigned __int8 **v121; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v122; // [rsp+60h] [rbp-A0h] BYREF
  struct IMetaDataImport2 *v123; // [rsp+68h] [rbp-98h]
  int v124; // [rsp+70h] [rbp-90h]
  unsigned int v125; // [rsp+74h] [rbp-8Ch]
  struct IMDInternalImport *v126; // [rsp+78h] [rbp-88h] BYREF
  int v127; // [rsp+80h] [rbp-80h]
  struct IMDInternalImport **v128; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v129; // [rsp+90h] [rbp-70h] BYREF
  int v130; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v131; // [rsp+A4h] [rbp-5Ch]
  LPVOID v132; // [rsp+B0h] [rbp-50h]
  __int16 v133; // [rsp+B8h] [rbp-48h] BYREF
  int v134; // [rsp+140h] [rbp+40h] BYREF
  __int64 v135; // [rsp+144h] [rbp+44h]
  LPVOID lpMem; // [rsp+150h] [rbp+50h]
  __int16 v137; // [rsp+158h] [rbp+58h] BYREF
  LPVOID v138[68]; // [rsp+260h] [rbp+160h] BYREF

  v124 = 0;
  RvaData = PEDecoder::GetRvaData((char *)this + 64, a2, 0);
  v122 = RvaData + 1;
  v6 = *(_BYTE *)DacInstantiateTypeByAddressHelper(RvaData, 1u, 1, 1);
  v7 = (struct IMetaDataImport2 *)*((_QWORD *)this + 29);
  if ( (v6 & 0x80u) != 0 )
  {
    v8 = (char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1);
    v9 = v122;
    if ( *v8 < 0 )
    {
      v11 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) & 0xC0) == 0x80;
      v12 = v122++;
      if ( v11 )
      {
        v13 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v12, 1u, 1, 1) & 0x3F) << 8;
      }
      else
      {
        v14 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v12, 1u, 1, 1) & 0x1F) << 24;
        v15 = v122++;
        v16 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v15, 1u, 1, 1) << 16) | v14;
        v17 = v122++;
        v13 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v17, 1u, 1, 1) << 8) | v16;
      }
      v18 = v122++;
      v10 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v18, 1u, 1, 1) | v13;
    }
    else
    {
      ++v122;
      v10 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v9, 1u, 1, 1);
    }
    v19 = (unsigned __int64 *)NativeImageDumper::OpenImport(this, v10);
    v6 &= ~0x80u;
    v20 = v19[1];
    if ( !v20 )
      return;
    v7 = *(struct IMetaDataImport2 **)(v20 + 40);
    v21 = *v19;
    if ( *(_WORD *)DacInstantiateTypeByAddressHelper(*v19, 4u, 1, 1) )
    {
      v22 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v21, 4u, 1, 1);
      v23 = NativeImageDumper::MapAssemblyRefToManifest(
              this,
              *v22 | 0x23000000,
              *((struct IMetaDataAssemblyImport **)this + 30));
      NativeImageDumper::AppendToken(this, v23, a3, *((struct IMetaDataImport2 **)this + 31));
      SString::Append(a3, L" ");
    }
    if ( *((_WORD *)DacInstantiateTypeByAddressHelper(v21, 4u, 1, 1) + 1) )
    {
      v24 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v21, 4u, 1, 1);
      NativeImageDumper::AppendToken(this, v24[1] | 0x26000000, a3, v7);
      SString::Append(a3, L" ");
    }
  }
  if ( v6 <= 0x50u )
  {
    if ( v6 == 80 )
      return;
    if ( v6 <= 0x15u )
    {
      if ( v6 != 21 )
      {
        if ( v6 != 16 )
        {
          if ( v6 == 17 )
            goto LABEL_111;
          if ( v6 != 18 )
          {
            if ( v6 != 19 )
            {
              if ( v6 == 20 )
              {
                v25 = L"Entrypoint for ";
LABEL_23:
                SString::Append(a3, v25);
                if ( *(char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) < 0 )
                {
                  v27 = DacSigUncompressBigData(&v122);
                }
                else
                {
                  v26 = v122++;
                  v27 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v26, 1u, 1, 1);
                }
                v28 = v27 | 0x6000000;
LABEL_86:
                NativeImageDumper::AppendTokenName(this, v28, a3, v7, 0);
                return;
              }
              goto LABEL_93;
            }
            goto LABEL_50;
          }
          goto LABEL_67;
        }
LABEL_62:
        if ( v7 )
        {
          NativeImageDumper::TypeToString(this, &v122, a3, v7, 0);
          return;
        }
        v40 = L"<unresolved type> ";
        goto LABEL_176;
      }
      v29 = L"Entrypoint for ref ";
LABEL_28:
      SString::Append(a3, v29);
      if ( *(char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) < 0 )
      {
        v31 = DacSigUncompressBigData(&v122);
      }
      else
      {
        v30 = v122++;
        v31 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v30, 1u, 1, 1);
      }
      v28 = v31 | 0xA000000;
      goto LABEL_86;
    }
    switch ( v6 )
    {
      case 0x16u:
LABEL_50:
        v39 = L"Entrypoint for ";
LABEL_110:
        SString::Append(a3, v39);
LABEL_111:
        v66 = (char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1);
        v67 = v122;
        if ( *v66 < 0 )
        {
          v11 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) & 0xC0) == 0x80;
          v69 = v122++;
          if ( v11 )
          {
            v70 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v69, 1u, 1, 1) & 0x3F) << 8;
          }
          else
          {
            v71 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v69, 1u, 1, 1) & 0x1F) << 24;
            v72 = v122++;
            v73 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v72, 1u, 1, 1) << 16) | v71;
            v74 = v122++;
            v70 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v74, 1u, 1, 1) << 8) | v73;
          }
          v75 = v122++;
          v68 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v75, 1u, 1, 1) | v70;
        }
        else
        {
          ++v122;
          v68 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v67, 1u, 1, 1);
        }
        v123 = v7;
        if ( v7 )
        {
          if ( (v68 & 0x40) != 0 )
            v123 = (struct IMetaDataImport2 *)NativeImageDumper::TypeToString(this, &v122, a3, v7, 0);
          v76 = (char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1);
          v77 = v122;
          if ( (v68 & 8) != 0 )
          {
            if ( *v76 < 0 )
            {
              v11 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) & 0xC0) == 0x80;
              v79 = v122++;
              if ( v11 )
              {
                v80 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v79, 1u, 1, 1) & 0x3F) << 8;
              }
              else
              {
                v81 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v79, 1u, 1, 1) & 0x1F) << 24;
                v82 = v122++;
                v83 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v82, 1u, 1, 1) << 16) | v81;
                v84 = v122++;
                v80 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v84, 1u, 1, 1) << 8) | v83;
              }
              v85 = v122++;
              v78 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v85, 1u, 1, 1) | v80;
            }
            else
            {
              ++v122;
              v78 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v77, 1u, 1, 1);
            }
            SString::AppendPrintf(a3, L" method slot %d", v78);
          }
          else
          {
            if ( *v76 < 0 )
            {
              v11 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) & 0xC0) == 0x80;
              v87 = v122++;
              if ( v11 )
              {
                v88 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v87, 1u, 1, 1) & 0x3F) << 8;
              }
              else
              {
                v89 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v87, 1u, 1, 1) & 0x1F) << 24;
                v90 = v122++;
                v91 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v90, 1u, 1, 1) << 16) | v89;
                v92 = v122++;
                v88 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v92, 1u, 1, 1) << 8) | v91;
              }
              v93 = v122++;
              v86 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v93, 1u, 1, 1) | v88;
            }
            else
            {
              ++v122;
              v86 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v77, 1u, 1, 1);
            }
            LODWORD(v128) = v68 & 0x10;
            v94 = v86 | ((_DWORD)v128 != 0 ? 167772160 : 100663296);
            SString::Append(a3, L" ");
            v131 = 128;
            v132 = &v133;
            v130 = 2;
            v133 = 0;
            v95 = v123;
            NativeImageDumper::AppendTokenName(this, v94, (struct SString *)&v130, v123, 0);
            if ( (v68 & 4) != 0 )
            {
              v96 = (char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1);
              v97 = v122;
              if ( *v96 < 0 )
              {
                v11 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) & 0xC0) == 0x80;
                v99 = v122++;
                if ( v11 )
                {
                  v100 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v99, 1u, 1, 1) & 0x3F) << 8;
                }
                else
                {
                  v101 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v99, 1u, 1, 1) & 0x1F) << 24;
                  v102 = v122++;
                  v103 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v102, 1u, 1, 1) << 16) | v101;
                  v104 = v122++;
                  v100 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v104, 1u, 1, 1) << 8) | v103;
                }
                v105 = v122++;
                v98 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v105, 1u, 1, 1) | v100;
              }
              else
              {
                ++v122;
                v98 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v97, 1u, 1, 1);
              }
              SString::Append((SString *)&v130, L"<");
              v106 = 0;
              for ( LODWORD(v123) = 0; v106 < v98; LODWORD(v123) = v106 )
              {
                if ( v106 )
                  SString::Append((SString *)&v130, L", ");
                NativeImageDumper::TypeToString(this, &v122, &v130, v7, 0);
                v106 = (_DWORD)v123 + 1;
              }
              SString::Append((SString *)&v130, L">");
            }
            v107 = *(_QWORD *)v95;
            if ( (_DWORD)v128 )
            {
              v121 = &v129;
              v108 = (*(__int64 (__fastcall **)(struct IMetaDataImport2 *, _QWORD, _QWORD, _QWORD, _DWORD))(v107 + 248))(
                       v95,
                       v94,
                       0,
                       0,
                       0);
              if ( v108 < 0 )
                ThrowHR(v108);
            }
            else
            {
              LODWORD(v121) = 0;
              v110 = (*(__int64 (__fastcall **)(struct IMetaDataImport2 *, _QWORD, _QWORD, _QWORD, _DWORD))(v107 + 240))(
                       v95,
                       v94,
                       0,
                       0,
                       0);
              if ( v110 < 0 )
                ThrowHR(v110);
            }
            v138[0] = 0;
            v138[1] = 0;
            v138[2] = (LPVOID)512;
            v127 = 0;
            v128 = &v126;
            v126 = 0;
            v124 = 1;
            MDInternalInterfaceFromPublic = GetMDInternalInterfaceFromPublic(v95, v109, &v126);
            if ( MDInternalInterfaceFromPublic < 0 )
              ThrowHR(MDInternalInterfaceFromPublic);
            v124 = 0;
            v112 = v127;
            if ( v126 )
              v112 = 1;
            v127 = v112;
            v135 = 256;
            lpMem = &v137;
            v134 = 2;
            v137 = 0;
            if ( (unsigned int)SString::IsRepresentation(&v130, 7) )
            {
              v113 = (const char *)v132;
            }
            else
            {
              SString::ConvertToANSI((SString *)&v130, (struct SString *)&v134);
              v113 = (const char *)lpMem;
            }
            v114 = PrettyPrintSig(v129, v125, v113, (struct CQuickBytes *)v138, v126, 0, (int)v121);
            SString::SetANSI((SString *)&v130, v114);
            SString::Append(a3, (const struct SString *)&v130);
            if ( (v135 & 0x800000000LL) != 0 )
            {
              v115 = lpMem;
              if ( lpMem )
              {
                ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                {
                  ProcessHeap = GetProcessHeap();
                  `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
                }
                HeapFree(ProcessHeap, 0, v115);
              }
            }
            if ( v127 )
            {
              if ( v126 )
                (*(void (__fastcall **)(struct IMDInternalImport *))(*(_QWORD *)v126 + 16LL))(v126);
              v127 = 0;
            }
            v117 = v138[0];
            if ( v138[0] )
            {
              v118 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                v118 = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = v118;
              }
              HeapFree(v118, 0, v117);
              v138[0] = 0;
            }
            if ( (v131 & 0x800000000LL) != 0 )
            {
              v119 = v132;
              if ( v132 )
              {
                v120 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                {
                  v120 = GetProcessHeap();
                  `ClrFreeInProcessHeap'::`2'::ProcessHeap = v120;
                }
                HeapFree(v120, 0, v119);
              }
            }
          }
          SString::Append(a3, L" flags=(");
          EnumFlagsToString(v68, (const struct NativeImageDumper::EnumMnemonics *)&qword_1801605D0, 7, L", ", a3);
          v40 = L")";
        }
        else
        {
          v40 = L"<unresolved method signature>";
        }
        goto LABEL_176;
      case 0x17u:
        v25 = L"Virtual call for ";
        goto LABEL_23;
      case 0x18u:
        v29 = L"Virtual call for ref ";
        goto LABEL_28;
      case 0x19u:
        SString::Append(a3, L"Virtual call for ");
        if ( *(char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) < 0 )
        {
          v38 = DacSigUncompressBigData(&v122);
        }
        else
        {
          v37 = v122++;
          v38 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v37, 1u, 1, 1);
        }
        SString::AppendPrintf(a3, L"slot %d ", v38);
        goto LABEL_62;
      case 0x1Bu:
        if ( *(char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) < 0 )
        {
          v33 = DacSigUncompressBigData(&v122);
        }
        else
        {
          v32 = v122++;
          v33 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v32, 1u, 1, 1);
        }
        v34 = v33 | 0x70000000;
        if ( !v7 )
        {
          SString::AppendPrintf(a3, L"<unresolved token %d>", v34);
          return;
        }
        goto LABEL_41;
    }
LABEL_93:
    v40 = L"Unknown fixup kind";
    goto LABEL_176;
  }
  if ( v6 > 0x56u )
  {
    switch ( v6 )
    {
      case 'W':
        v39 = L"Profiling handle for ";
        goto LABEL_110;
      case 'X':
      case 'Y':
        v63 = 167772160;
        break;
      case 'Z':
        v63 = 0x4000000;
        break;
      case '[':
        SString::Append(a3, L"Active dependency for  ");
        if ( *(char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) < 0 )
        {
          v58 = DacSigUncompressBigData(&v122);
        }
        else
        {
          v57 = v122++;
          v58 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v57, 1u, 1, 1);
        }
        v59 = (unsigned __int64 *)NativeImageDumper::OpenImport(this, v58);
        v60 = DacInstantiateTypeByAddressHelper(*v59, 4u, 1, 1);
        v61 = v60;
        if ( *v60 )
        {
          v62 = NativeImageDumper::MapAssemblyRefToManifest(
                  this,
                  (unsigned __int16)*v60 | 0x23000000,
                  *((struct IMetaDataAssemblyImport **)this + 30));
          NativeImageDumper::AppendToken(this, v62, a3, *((struct IMetaDataImport2 **)this + 31));
          SString::Append(a3, L" ");
        }
        if ( !v61[1] )
          return;
        v36 = (unsigned __int16)v61[1] | 0x26000000;
        v35 = *(struct IMetaDataImport2 **)(v59[1] + 40);
LABEL_101:
        NativeImageDumper::AppendToken(this, v36, a3, v35);
        return;
      default:
        goto LABEL_93;
    }
    if ( *(char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) < 0 )
    {
      v65 = DacSigUncompressBigData(&v122);
    }
    else
    {
      v64 = v122++;
      v65 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v64, 1u, 1, 1);
    }
    v34 = v63 | v65;
    if ( !v7 )
    {
      SString::AppendPrintf(a3, "<unresolved token %d>", v34);
      return;
    }
LABEL_41:
    v35 = v7;
    v36 = v34;
    goto LABEL_101;
  }
  if ( v6 == 86 )
  {
    v40 = L"Indirect P/Invoke target for ";
    goto LABEL_176;
  }
  if ( v6 != 81 )
  {
    if ( v6 != 82 )
    {
      switch ( v6 )
      {
        case 'S':
          v41 = L"Module For Statics for ";
          break;
        case 'T':
          v41 = L"Statics ID for ";
          break;
        case 'U':
          v40 = L"Synchronization handle for ";
LABEL_176:
          SString::Append(a3, v40);
          return;
        default:
          goto LABEL_93;
      }
      SString::Append(a3, v41);
      goto LABEL_62;
    }
    v40 = L"Module For Statics";
    goto LABEL_176;
  }
  SString::Append(a3, L"Static field address for ");
LABEL_67:
  v42 = (char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1);
  v43 = v122;
  if ( *v42 < 0 )
  {
    v11 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1) & 0xC0) == 0x80;
    v45 = v122++;
    if ( v11 )
    {
      DacInstantiateTypeByAddressHelper(v45, 1u, 1, 1);
      LOBYTE(v46) = 0;
    }
    else
    {
      v47 = (*(_BYTE *)DacInstantiateTypeByAddressHelper(v45, 1u, 1, 1) & 0x1F) << 24;
      v48 = v122++;
      v49 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v48, 1u, 1, 1) << 16) | v47;
      v50 = v122++;
      v46 = (*(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v50, 1u, 1, 1) << 8) | v49;
    }
    v51 = v122++;
    v44 = *(_BYTE *)DacInstantiateTypeByAddressHelper(v51, 1u, 1, 1) | v46;
  }
  else
  {
    ++v122;
    v44 = *(_BYTE *)DacInstantiateTypeByAddressHelper(v43, 1u, 1, 1);
  }
  if ( v7 )
  {
    if ( (v44 & 0x40) != 0 )
      v7 = (struct IMetaDataImport2 *)NativeImageDumper::TypeToString(this, &v122, a3, v7, 0);
  }
  else
  {
    SString::Append(a3, L"<unresolved type>");
  }
  v52 = (char *)DacInstantiateTypeByAddressHelper(v122, 1u, 1, 1);
  if ( (v44 & 8) == 0 )
  {
    if ( *v52 < 0 )
    {
      v56 = DacSigUncompressBigData(&v122);
    }
    else
    {
      v55 = v122++;
      v56 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v55, 1u, 1, 1);
    }
    SString::Append(a3, L" ");
    v28 = v56 | ((v44 & 0x10) != 0 ? 167772160 : 0x4000000);
    goto LABEL_86;
  }
  if ( *v52 < 0 )
  {
    v54 = DacSigUncompressBigData(&v122);
  }
  else
  {
    v53 = v122++;
    v54 = *(unsigned __int8 *)DacInstantiateTypeByAddressHelper(v53, 1u, 1, 1);
  }
  SString::AppendPrintf(a3, L" field index %d", v54);
}

```

## disassembly

```asm
0x1800476dc  mov     [rsp-8+arg_18], rbx
0x1800476e1  push    rbp
0x1800476e2  push    rsi
0x1800476e3  push    rdi
0x1800476e4  push    r12
0x1800476e6  push    r13
0x1800476e8  push    r14
0x1800476ea  push    r15
0x1800476ec  lea     rbp, [rsp-390h]
0x1800476f4  sub     rsp, 490h
0x1800476fb  mov     rax, cs:__security_cookie
0x180047702  xor     rax, rsp
0x180047705  mov     [rbp+3C0h+var_40], rax
0x18004770c  mov     rdi, r8
0x18004770f  mov     rsi, rcx
0x180047712  xor     r12d, r12d
0x180047715  mov     [rsp+4C0h+var_450], r12d
0x18004771a  add     rcx, 40h ; '@'
0x18004771e  xor     r8d, r8d
0x180047721  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x180047726  lea     rcx, [rax+1]
0x18004772a  mov     [rsp+4C0h+var_460], rcx
0x18004772f  lea     r13d, [r12+1]
0x180047734  mov     r9b, r13b; bool
0x180047737  mov     r8b, r13b; bool
0x18004773a  mov     edx, r13d; unsigned int
0x18004773d  mov     rcx, rax; unsigned __int64
0x180047740  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047745  mov     r15b, [rax]
0x180047748  mov     r14, [rsi+0E8h]
0x18004774f  test    r15b, r15b
0x180047752  jns     loc_18004791E
0x180047758  mov     r9b, r13b; bool
0x18004775b  mov     r8b, r13b; bool
0x18004775e  mov     edx, r13d; unsigned int
0x180047761  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047766  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004776b  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047770  mov     r9b, r13b; bool
0x180047773  mov     r8b, r13b; bool
0x180047776  mov     edx, r13d; unsigned int
0x180047779  cmp     [rax], r12b
0x18004777c  jl      short loc_180047794
0x18004777e  lea     rax, [rcx+1]
0x180047782  mov     [rsp+4C0h+var_460], rax
0x180047787  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004778c  movzx   ebx, byte ptr [rax]
0x18004778f  jmp     loc_180047841
0x180047794  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047799  mov     cl, [rax]
0x18004779b  and     cl, 0C0h
0x18004779e  mov     r9b, r13b; bool
0x1800477a1  mov     r8b, r13b; bool
0x1800477a4  mov     edx, r13d; unsigned int
0x1800477a7  cmp     cl, 80h
0x1800477aa  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x1800477af  lea     rax, [rcx+1]
0x1800477b3  mov     [rsp+4C0h+var_460], rax
0x1800477b8  jnz     short loc_1800477CA
0x1800477ba  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800477bf  movzx   ebx, byte ptr [rax]
0x1800477c2  and     ebx, 3Fh
0x1800477c5  shl     ebx, 8
0x1800477c8  jmp     short loc_180047820
0x1800477ca  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800477cf  movzx   ebx, byte ptr [rax]
0x1800477d2  and     ebx, 1Fh
0x1800477d5  shl     ebx, 18h
0x1800477d8  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x1800477dd  lea     rax, [rcx+1]
0x1800477e1  mov     [rsp+4C0h+var_460], rax
0x1800477e6  mov     r9b, r13b; bool
0x1800477e9  mov     r8b, r13b; bool
0x1800477ec  mov     edx, r13d; unsigned int
0x1800477ef  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800477f4  movzx   ecx, byte ptr [rax]
0x1800477f7  shl     ecx, 10h
0x1800477fa  or      ebx, ecx
0x1800477fc  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047801  lea     rax, [rcx+1]
0x180047805  mov     [rsp+4C0h+var_460], rax
0x18004780a  mov     r9b, r13b; bool
0x18004780d  mov     r8b, r13b; bool
0x180047810  mov     edx, r13d; unsigned int
0x180047813  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047818  movzx   ecx, byte ptr [rax]
0x18004781b  shl     ecx, 8
0x18004781e  or      ebx, ecx
0x180047820  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047825  lea     rax, [rcx+1]
0x180047829  mov     [rsp+4C0h+var_460], rax
0x18004782e  mov     r9b, r13b; bool
0x180047831  mov     r8b, r13b; bool
0x180047834  mov     edx, r13d; unsigned int
0x180047837  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004783c  movzx   ecx, byte ptr [rax]
0x18004783f  or      ebx, ecx
0x180047841  mov     edx, ebx; int
0x180047843  mov     rcx, rsi; this
0x180047846  call    ?OpenImport@NativeImageDumper@@AEAAPEAUImport@1@H@Z; NativeImageDumper::OpenImport(int)
0x18004784b  and     r15b, 7Fh
0x18004784f  mov     r14, [rax+8]
0x180047853  test    r14, r14
0x180047856  jz      loc_1800486C3
0x18004785c  mov     r14, [r14+28h]
0x180047860  mov     rbx, [rax]
0x180047863  mov     r9b, r13b; bool
0x180047866  mov     r8b, r13b; bool
0x180047869  mov     edx, 4; unsigned int
0x18004786e  mov     rcx, rbx; unsigned __int64
0x180047871  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047876  cmp     [rax], r12w
0x18004787a  jz      short loc_1800478CA
0x18004787c  mov     r9b, r13b; bool
0x18004787f  mov     r8b, r13b; bool
0x180047882  mov     edx, 4; unsigned int
0x180047887  mov     rcx, rbx; unsigned __int64
0x18004788a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004788f  movzx   edx, word ptr [rax]
0x180047892  or      edx, 23000000h; unsigned int
0x180047898  mov     r8, [rsi+0F0h]; struct IMetaDataAssemblyImport *
0x18004789f  mov     rcx, rsi; this
0x1800478a2  call    ?MapAssemblyRefToManifest@NativeImageDumper@@AEAAIIPEAUIMetaDataAssemblyImport@@@Z; NativeImageDumper::MapAssemblyRefToManifest(uint,IMetaDataAssemblyImport *)
0x1800478a7  mov     r9, [rsi+0F8h]; struct IMetaDataImport2 *
0x1800478ae  mov     r8, rdi; struct SString *
0x1800478b1  mov     edx, eax; unsigned int
0x1800478b3  mov     rcx, rsi; this
0x1800478b6  call    ?AppendToken@NativeImageDumper@@QEAAXIAEAVSString@@PEAUIMetaDataImport2@@@Z; NativeImageDumper::AppendToken(uint,SString &,IMetaDataImport2 *)
0x1800478bb  lea     rdx, asc_180137874; " "
0x1800478c2  mov     rcx, rdi; this
0x1800478c5  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800478ca  mov     r9b, r13b; bool
0x1800478cd  mov     r8b, r13b; bool
0x1800478d0  mov     edx, 4; unsigned int
0x1800478d5  mov     rcx, rbx; unsigned __int64
0x1800478d8  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800478dd  cmp     [rax+2], r12w
0x1800478e2  jz      short loc_18004791E
0x1800478e4  mov     r9b, r13b; bool
0x1800478e7  mov     r8b, r13b; bool
0x1800478ea  mov     edx, 4; unsigned int
0x1800478ef  mov     rcx, rbx; unsigned __int64
0x1800478f2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800478f7  movzx   edx, word ptr [rax+2]
0x1800478fb  or      edx, 26000000h; unsigned int
0x180047901  mov     r9, r14; struct IMetaDataImport2 *
0x180047904  mov     r8, rdi; struct SString *
0x180047907  mov     rcx, rsi; this
0x18004790a  call    ?AppendToken@NativeImageDumper@@QEAAXIAEAVSString@@PEAUIMetaDataImport2@@@Z; NativeImageDumper::AppendToken(uint,SString &,IMetaDataImport2 *)
0x18004790f  lea     rdx, asc_180137874; " "
0x180047916  mov     rcx, rdi; this
0x180047919  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18004791e  movzx   ecx, r15b
0x180047922  cmp     ecx, 50h ; 'P'
0x180047925  ja      loc_180047B4A
0x18004792b  jz      loc_1800486C3
0x180047931  cmp     ecx, 15h
0x180047934  ja      loc_180047A29
0x18004793a  jz      loc_1800479CB
0x180047940  sub     ecx, 10h
0x180047943  jz      loc_180047B9A
0x180047949  sub     ecx, r13d
0x18004794c  jz      loc_180047F6C
0x180047952  sub     ecx, r13d
0x180047955  jz      loc_180047BE3
0x18004795b  sub     ecx, r13d
0x18004795e  jz      loc_180047B3E
0x180047964  cmp     ecx, r13d
0x180047967  jnz     loc_180047DFD
0x18004796d  lea     rdx, aEntrypointFor; "Entrypoint for "
0x180047974  mov     rcx, rdi; this
0x180047977  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18004797c  mov     r9b, r13b; bool
0x18004797f  mov     r8b, r13b; bool
0x180047982  mov     edx, r13d; unsigned int
0x180047985  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x18004798a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004798f  cmp     [rax], r12b
0x180047992  jl      short loc_1800479B5
0x180047994  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047999  lea     rax, [rcx+1]
0x18004799d  mov     [rsp+4C0h+var_460], rax
0x1800479a2  mov     r9b, r13b; bool
0x1800479a5  mov     r8b, r13b; bool
0x1800479a8  mov     edx, r13d; unsigned int
0x1800479ab  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800479b0  movzx   eax, byte ptr [rax]
0x1800479b3  jmp     short loc_1800479BF
0x1800479b5  lea     rcx, [rsp+4C0h+var_460]
0x1800479ba  call    ?DacSigUncompressBigData@@YAKAEAV?$__DPtr@$$CBE@@@Z; DacSigUncompressBigData(__DPtr<uchar const> &)
0x1800479bf  or      eax, 6000000h
0x1800479c4  mov     edx, eax
0x1800479c6  jmp     loc_180047DB0
0x1800479cb  lea     rdx, aEntrypointForR; "Entrypoint for ref "
0x1800479d2  mov     rcx, rdi; this
0x1800479d5  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800479da  mov     r9b, r13b; bool
0x1800479dd  mov     r8b, r13b; bool
0x1800479e0  mov     edx, r13d; unsigned int
0x1800479e3  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x1800479e8  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800479ed  cmp     [rax], r12b
0x1800479f0  jl      short loc_180047A13
0x1800479f2  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x1800479f7  lea     rax, [rcx+1]
0x1800479fb  mov     [rsp+4C0h+var_460], rax
0x180047a00  mov     r9b, r13b; bool
0x180047a03  mov     r8b, r13b; bool
0x180047a06  mov     edx, r13d; unsigned int
0x180047a09  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047a0e  movzx   eax, byte ptr [rax]
0x180047a11  jmp     short loc_180047A1D
0x180047a13  lea     rcx, [rsp+4C0h+var_460]
0x180047a18  call    ?DacSigUncompressBigData@@YAKAEAV?$__DPtr@$$CBE@@@Z; DacSigUncompressBigData(__DPtr<uchar const> &)
0x180047a1d  mov     edx, 0A000000h
0x180047a22  or      edx, eax
0x180047a24  jmp     loc_180047DB0
0x180047a29  sub     ecx, 16h
0x180047a2c  jz      loc_180047B3E
0x180047a32  sub     ecx, r13d
0x180047a35  jz      loc_180047B32
0x180047a3b  sub     ecx, r13d
0x180047a3e  jz      loc_180047B26
0x180047a44  sub     ecx, r13d
0x180047a47  jz      short loc_180047AC0
0x180047a49  cmp     ecx, 2
0x180047a4c  jnz     loc_180047DFD
0x180047a52  mov     r9b, r13b; bool
0x180047a55  mov     r8b, r13b; bool
0x180047a58  mov     edx, r13d; unsigned int
0x180047a5b  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047a60  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047a65  cmp     [rax], r12b
0x180047a68  jl      short loc_180047A8B
0x180047a6a  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047a6f  lea     rax, [rcx+1]
0x180047a73  mov     [rsp+4C0h+var_460], rax
0x180047a78  mov     r9b, r13b; bool
0x180047a7b  mov     r8b, r13b; bool
0x180047a7e  mov     edx, r13d; unsigned int
0x180047a81  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047a86  movzx   eax, byte ptr [rax]
0x180047a89  jmp     short loc_180047A95
0x180047a8b  lea     rcx, [rsp+4C0h+var_460]
0x180047a90  call    ?DacSigUncompressBigData@@YAKAEAV?$__DPtr@$$CBE@@@Z; DacSigUncompressBigData(__DPtr<uchar const> &)
0x180047a95  or      eax, 70000000h
0x180047a9a  test    r14, r14
0x180047a9d  jz      short loc_180047AA9
0x180047a9f  mov     r9, r14
0x180047aa2  mov     edx, eax
0x180047aa4  jmp     loc_180047EDC
0x180047aa9  lea     rdx, aUnresolvedToke; "<unresolved token %d>"
0x180047ab0  mov     r8d, eax
0x180047ab3  mov     rcx, rdi; this
0x180047ab6  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x180047abb  jmp     loc_1800486C3
0x180047ac0  lea     rdx, aVirtualCallFor_0; "Virtual call for "
0x180047ac7  mov     rcx, rdi; this
0x180047aca  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180047acf  mov     r9b, r13b; bool
0x180047ad2  mov     r8b, r13b; bool
0x180047ad5  mov     edx, r13d; unsigned int
0x180047ad8  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047add  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047ae2  cmp     [rax], r12b
0x180047ae5  jl      short loc_180047B08
0x180047ae7  mov     rcx, [rsp+4C0h+var_460]; unsigned __int64
0x180047aec  lea     rax, [rcx+1]
0x180047af0  mov     [rsp+4C0h+var_460], rax
0x180047af5  mov     r9b, r13b; bool
0x180047af8  mov     r8b, r13b; bool
0x180047afb  mov     edx, r13d; unsigned int
0x180047afe  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180047b03  movzx   eax, byte ptr [rax]
0x180047b06  jmp     short loc_180047B12
0x180047b08  lea     rcx, [rsp+4C0h+var_460]
0x180047b0d  call    ?DacSigUncompressBigData@@YAKAEAV?$__DPtr@$$CBE@@@Z; DacSigUncompressBigData(__DPtr<uchar const> &)
0x180047b12  mov     r8d, eax
0x180047b15  lea     rdx, aSlotD_0; "slot %d "
0x180047b1c  mov     rcx, rdi; this
0x180047b1f  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x180047b24  jmp     short loc_180047B9A
0x180047b26  lea     rdx, aVirtualCallFor; "Virtual call for ref "
0x180047b2d  jmp     loc_1800479D2
0x180047b32  lea     rdx, aVirtualCallFor_0; "Virtual call for "
0x180047b39  jmp     loc_180047974
0x180047b3e  lea     rdx, aEntrypointFor; "Entrypoint for "
0x180047b45  jmp     loc_180047F64
0x180047b4a  cmp     ecx, 56h ; 'V'
0x180047b4d  ja      loc_180047DD4
0x180047b53  jz      loc_180047DC8
0x180047b59  sub     ecx, 51h ; 'Q'
0x180047b5c  jz      short loc_180047BD4
0x180047b5e  sub     ecx, r13d
0x180047b61  jz      short loc_180047BC8
0x180047b63  sub     ecx, r13d
0x180047b66  jz      short loc_180047B8B
0x180047b68  sub     ecx, r13d
0x180047b6b  jz      short loc_180047B82
0x180047b6d  cmp     ecx, r13d
  ... truncated ...
```
