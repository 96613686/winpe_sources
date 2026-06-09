# CSecurityAdmin2::RecursiveUpdateNode(_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,void *,int,int)

- ea: `0x180027a1c`
- end: `0x180028004`
- name: `?RecursiveUpdateNode@CSecurityAdmin2@@QEAAJPEAU_GUID@@000PEAK1PEAXHH@Z`
- size: `1512`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this, struct _GUID *, struct _GUID *, struct _GUID *, struct _GUID *, unsigned int *, unsigned int *, void *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180027a1c`
- `0x18002800c`

## callees

- `0x180009574`
- `0x1800269a8`
- `0x180027660`
- `0x180027890`
- `0x180027a1c`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180027d3f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180027de7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180027d3f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180027de7`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180027b4c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180027b4c`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180027fd5`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180027fd5`

## pseudocode

```c
__int64 __fastcall CSecurityAdmin2::RecursiveUpdateNode(
        struct ISimpleTableDispenser **this,
        struct _GUID *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        struct _GUID *a5,
        unsigned int *a6,
        unsigned int *a7,
        void *a8,
        int a9,
        int a10)
{
  int v12; // edi
  int NodeTable; // ebx
  __int64 result; // rax
  const struct _GUID *v15; // r8
  struct ISimpleTableDispenser *v16; // rdx
  PSECURITY_DESCRIPTOR v17; // rbx
  __int64 (__fastcall *v18)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR); // rdi
  DWORD SecurityDescriptorLength; // eax
  void *v20; // rcx
  PSECURITY_DESCRIPTOR v21; // rbx
  __int64 (__fastcall *v22)(struct ISimpleTableWrite *, _QWORD, _QWORD, PSECURITY_DESCRIPTOR); // rdi
  DWORD v23; // eax
  struct ISimpleTableWrite *v24; // rcx
  struct _GUID *v25; // r14
  struct _GUID *v26; // rdi
  __int64 (__fastcall *v27)(struct ISimpleTableWrite *, _QWORD, _QWORD, _QWORD, unsigned int **); // rax
  int updated; // eax
  unsigned int v29; // [rsp+30h] [rbp-D0h]
  struct ISimpleTableWrite *v30; // [rsp+60h] [rbp-A0h] BYREF
  void *v31; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v32; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v33; // [rsp+74h] [rbp-8Ch] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v36; // [rsp+84h] [rbp-7Ch] BYREF
  void *v37; // [rsp+88h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID *v39; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID *v40; // [rsp+A0h] [rbp-60h]
  struct _GUID *v41; // [rsp+A8h] [rbp-58h]
  struct _GUID *v42; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int *v43; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v44; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v45[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v46; // [rsp+E0h] [rbp-20h]
  int v47; // [rsp+E4h] [rbp-1Ch]
  struct _GUID *v48; // [rsp+E8h] [rbp-18h]
  int v49; // [rsp+F0h] [rbp-10h]
  int v50; // [rsp+F4h] [rbp-Ch]
  int v51; // [rsp+F8h] [rbp-8h]
  int v52; // [rsp+FCh] [rbp-4h]
  struct _GUID *v53; // [rsp+100h] [rbp+0h]
  int v54; // [rsp+108h] [rbp+8h]
  int v55; // [rsp+10Ch] [rbp+Ch]
  int v56; // [rsp+110h] [rbp+10h]
  int v57; // [rsp+114h] [rbp+14h]
  struct _GUID *v58; // [rsp+118h] [rbp+18h]
  int v59; // [rsp+120h] [rbp+20h]
  int v60; // [rsp+124h] [rbp+24h]
  int v61; // [rsp+128h] [rbp+28h]
  int v62; // [rsp+12Ch] [rbp+2Ch]
  void *v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+138h] [rbp+38h]
  int v65; // [rsp+13Ch] [rbp+3Ch]
  int v66; // [rsp+140h] [rbp+40h]
  int v67; // [rsp+144h] [rbp+44h]
  unsigned int *v68; // [rsp+148h] [rbp+48h]
  int v69; // [rsp+150h] [rbp+50h]
  int v70; // [rsp+154h] [rbp+54h]
  int v71; // [rsp+158h] [rbp+58h]
  int v72; // [rsp+15Ch] [rbp+5Ch]

  v37 = a8;
  v40 = a4;
  v41 = a3;
  if ( !a2 || a6 && !a5 || !a7 )
    return 2147942487LL;
  v30 = 0;
  v12 = 1;
  if ( !a9 )
    v12 = a10;
  v32 = 0;
  LODWORD(v31) = 0;
  v33 = 0;
  v35 = 0;
  pSecurityDescriptor = 0;
  ObjectDescriptor = 0;
  v39 = 0;
  v43 = 0;
  v44 = 0;
  NodeTable = CSecurityAdmin2::GetNodeTable(
                (CSecurityAdmin2 *)this,
                a2,
                a3,
                a4,
                a5,
                a6,
                a7,
                &v30,
                &v44,
                &v32,
                (unsigned int *)&v31);
  if ( NodeTable < 0 )
    goto LABEL_45;
  result = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, int *, _QWORD, PSECURITY_DESCRIPTOR *))(*(_QWORD *)v30 + 64LL))(
             v30,
             v32,
             &v35,
             0,
             &pSecurityDescriptor);
  if ( (int)result < 0 )
    return result;
  if ( !pSecurityDescriptor || IsValidSecurityDescriptor(pSecurityDescriptor) )
  {
    NodeTable = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, int *, _QWORD, struct _GUID **))(*(_QWORD *)v30 + 64LL))(
                  v30,
                  (unsigned int)v31,
                  &v35,
                  0,
                  &v39);
    if ( NodeTable >= 0 )
    {
      NodeTable = CSecurityAdmin2::BuildSecurityDescriptorForRoleSet(
                    this,
                    v37,
                    (struct _GUID *)pSecurityDescriptor,
                    &ObjectDescriptor,
                    v39,
                    v12);
      if ( NodeTable >= 0 )
      {
        NodeTable = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 128LL))(v30);
        if ( NodeTable >= 0 )
        {
          if ( a6 )
          {
            v37 = 0;
            if ( (*(int (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, void **))(*(_QWORD *)v30 + 64LL))(
                   v30,
                   9,
                   0,
                   0,
                   &v37) >= 0 )
            {
              v48 = v41;
              v53 = v40;
              v63 = v37;
              v66 = 19;
              v71 = 19;
              v47 = 16;
              v52 = 16;
              v57 = 16;
              v62 = 16;
              v46 = 72;
              v51 = 72;
              v56 = 72;
              v61 = 72;
              v16 = this[6];
              v45[0] = a2;
              v45[1] = 0;
              v49 = 0;
              v50 = 1;
              v54 = 0;
              v55 = 2;
              v58 = a5;
              v59 = 0;
              v60 = 3;
              v64 = 0;
              v65 = 4;
              v67 = 4;
              v68 = a7;
              v69 = 0;
              v70 = 5;
              v72 = 4;
              v31 = 0;
              if ( (int)CSecurityAdmin2::GetTable(
                          (CSecurityAdmin2 *)4,
                          v16,
                          v15,
                          &tidCOMSERVICES_CLASSITFDISPID,
                          v45,
                          (void *)6,
                          v29,
                          0x20000u,
                          &v31) < 0
                || (*(int (__fastcall **)(void *))(*(_QWORD *)v31 + 24LL))(v31) < 0
                || (*(int (__fastcall **)(void *, _QWORD))(*(_QWORD *)v31 + 48LL))(v31, 0) < 0 )
              {
                v20 = v31;
              }
              else
              {
                NodeTable = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 128LL))(v31);
                if ( NodeTable >= 0 )
                {
                  v17 = ObjectDescriptor;
                  v18 = *(__int64 (__fastcall **)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v31 + 160LL);
                  SecurityDescriptorLength = GetSecurityDescriptorLength(ObjectDescriptor);
                  NodeTable = v18(v31, 6, SecurityDescriptorLength, v17);
                  if ( NodeTable >= 0 )
                  {
                    NodeTable = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 144LL))(v31);
                    if ( NodeTable >= 0 )
                      NodeTable = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 96LL))(v31);
                  }
                }
                v20 = v31;
                if ( v31 )
                {
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
                  v20 = 0;
                  v31 = 0;
                }
                if ( NodeTable < 0 )
                  goto LABEL_45;
              }
              if ( v20 )
                (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
          v21 = ObjectDescriptor;
          v22 = *(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v30 + 160LL);
          v23 = GetSecurityDescriptorLength(ObjectDescriptor);
          NodeTable = v22(v30, v32, v23, v21);
          if ( NodeTable >= 0 )
          {
            NodeTable = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 144LL))(v30);
            if ( NodeTable >= 0 )
            {
              NodeTable = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 96LL))(v30);
              if ( NodeTable >= 0 )
              {
                v24 = v30;
                v42 = 0;
                v36 = 0;
                if ( v30 )
                {
                  (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 16LL))(v30);
                  v24 = 0;
                  v30 = 0;
                }
                if ( a6 )
                  goto LABEL_46;
                v25 = v40;
                v26 = v41;
                NodeTable = CSecurityAdmin2::GetSubTable(
                              (CSecurityAdmin2 *)this,
                              a2,
                              v41,
                              v40,
                              a5,
                              0,
                              a7,
                              &v30,
                              &v44,
                              &v33);
                if ( NodeTable >= 0 )
                {
                  do
                  {
                    if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 40LL))(v30) < 0 )
                      break;
                    v27 = *(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _QWORD, _QWORD, unsigned int **))(*(_QWORD *)v30 + 64LL);
                    if ( a5 )
                    {
                      NodeTable = v27(v30, v33, 0, 0, &v43);
                      if ( NodeTable < 0 )
                        break;
                      v36 = *v43;
                      updated = CSecurityAdmin2::RecursiveUpdateNode(
                                  (CSecurityAdmin2 *)this,
                                  a2,
                                  v26,
                                  v25,
                                  a5,
                                  &v36,
                                  a7,
                                  ObjectDescriptor,
                                  0,
                                  a10);
                    }
                    else
                    {
                      NodeTable = v27(v30, v33, 0, 0, (unsigned int **)&v42);
                      if ( NodeTable < 0 )
                        break;
                      updated = CSecurityAdmin2::RecursiveUpdateNode(
                                  (CSecurityAdmin2 *)this,
                                  a2,
                                  v26,
                                  v25,
                                  v42,
                                  0,
                                  a7,
                                  ObjectDescriptor,
                                  0,
                                  a10);
                    }
                    NodeTable = updated;
                  }
                  while ( updated >= 0 );
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    NodeTable = -2147418113;
  }
LABEL_45:
  v24 = v30;
LABEL_46:
  if ( v24 )
  {
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v24 + 16LL))(v24);
    v30 = 0;
  }
  if ( ObjectDescriptor )
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
  return (unsigned int)NodeTable;
}

```

## disassembly

```asm
0x180027a1c  push    rbp
0x180027a1e  push    rbx
0x180027a1f  push    rsi
0x180027a20  push    rdi
0x180027a21  push    r12
0x180027a23  push    r13
0x180027a25  push    r14
0x180027a27  push    r15
0x180027a29  lea     rbp, [rsp-78h]
0x180027a2e  sub     rsp, 178h
0x180027a35  mov     rax, cs:__security_cookie
0x180027a3c  xor     rax, rsp
0x180027a3f  mov     [rbp+0B0h+var_50], rax
0x180027a43  mov     rax, [rbp+0B0h+arg_38]
0x180027a4a  mov     r12, rdx
0x180027a4d  mov     rsi, [rbp+0B0h+arg_20]
0x180027a54  mov     r13, rcx
0x180027a57  mov     r14, [rbp+0B0h+arg_28]
0x180027a5e  mov     r15, [rbp+0B0h+arg_30]
0x180027a65  mov     [rbp+0B0h+var_128], rax
0x180027a69  xor     eax, eax
0x180027a6b  mov     [rbp+0B0h+var_110], r9
0x180027a6f  mov     [rbp+0B0h+var_108], r8
0x180027a73  test    rdx, rdx
0x180027a76  jz      loc_180027FDF
0x180027a7c  test    r14, r14
0x180027a7f  jz      short loc_180027A8A
0x180027a81  test    rsi, rsi
0x180027a84  jz      loc_180027FDF
0x180027a8a  test    r15, r15
0x180027a8d  jz      loc_180027FDF
0x180027a93  cmp     [rbp+0B0h+arg_40], eax
0x180027a99  xorps   xmm0, xmm0
0x180027a9c  mov     [rsp+1B0h+var_150], rax
0x180027aa1  mov     edi, 1
0x180027aa6  cmovz   edi, [rbp+0B0h+arg_48]
0x180027aad  mov     [rsp+1B0h+var_140], eax
0x180027ab1  mov     dword ptr [rsp+1B0h+var_148], eax
0x180027ab5  mov     [rsp+1B0h+var_13C], eax
0x180027ab9  mov     [rbp+0B0h+var_130], eax
0x180027abc  mov     [rbp+0B0h+pSecurityDescriptor], rax
0x180027ac0  mov     [rsp+1B0h+ObjectDescriptor], rax
0x180027ac5  mov     [rbp+0B0h+var_118], rax
0x180027ac9  mov     [rbp+0B0h+var_F8], rax
0x180027acd  lea     rax, [rsp+1B0h+var_148]
0x180027ad2  mov     [rsp+1B0h+var_160], rax; unsigned int *
0x180027ad7  lea     rax, [rsp+1B0h+var_140]
0x180027adc  mov     [rsp+1B0h+var_168], rax; unsigned int *
0x180027ae1  lea     rax, [rbp+0B0h+var_F0]
0x180027ae5  mov     [rsp+1B0h+var_170], rax; struct _GUID *
0x180027aea  lea     rax, [rsp+1B0h+var_150]
0x180027aef  mov     [rsp+1B0h+var_178], rax; struct ISimpleTableWrite **
0x180027af4  mov     [rsp+1B0h+var_180], r15; unsigned int
0x180027af9  mov     [rsp+1B0h+var_188], r14; unsigned int *
0x180027afe  mov     [rsp+1B0h+var_190], rsi; struct _GUID *
0x180027b03  movups  xmmword ptr [rbp+0B0h+var_F0.Data1], xmm0
0x180027b07  call    ?GetNodeTable@CSecurityAdmin2@@QEAAJPEAU_GUID@@000PEAK1PEAPEAUISimpleTableWrite@@011@Z; CSecurityAdmin2::GetNodeTable(_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,ISimpleTableWrite * *,_GUID *,ulong *,ulong *)
0x180027b0c  mov     ebx, eax
0x180027b0e  test    eax, eax
0x180027b10  js      loc_180027FA9
0x180027b16  mov     rcx, [rsp+1B0h+var_150]
0x180027b1b  lea     rdx, [rbp+0B0h+pSecurityDescriptor]
0x180027b1f  mov     [rsp+1B0h+var_190], rdx
0x180027b24  lea     r8, [rbp+0B0h+var_130]
0x180027b28  mov     edx, [rsp+1B0h+var_140]
0x180027b2c  xor     r9d, r9d
0x180027b2f  mov     rax, [rcx]
0x180027b32  mov     rax, [rax+40h]
0x180027b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b3b  test    eax, eax
0x180027b3d  js      loc_180027FE4
0x180027b43  mov     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180027b47  test    rcx, rcx
0x180027b4a  jz      short loc_180027B60
0x180027b4c  call    cs:__imp_IsValidSecurityDescriptor
0x180027b52  test    eax, eax
0x180027b54  jnz     short loc_180027B60
0x180027b56  mov     ebx, 8000FFFFh
0x180027b5b  jmp     loc_180027FA9
0x180027b60  mov     rcx, [rsp+1B0h+var_150]
0x180027b65  lea     rdx, [rbp+0B0h+var_118]
0x180027b69  mov     [rsp+1B0h+var_190], rdx
0x180027b6e  lea     r8, [rbp+0B0h+var_130]
0x180027b72  mov     edx, dword ptr [rsp+1B0h+var_148]
0x180027b76  xor     r9d, r9d
0x180027b79  mov     rax, [rcx]
0x180027b7c  mov     rax, [rax+40h]
0x180027b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b85  mov     ebx, eax
0x180027b87  test    eax, eax
0x180027b89  js      loc_180027FA9
0x180027b8f  mov     rax, [rbp+0B0h+var_118]
0x180027b93  lea     r9, [rsp+1B0h+ObjectDescriptor]; void **
0x180027b98  mov     r8, [rbp+0B0h+pSecurityDescriptor]; void *
0x180027b9c  mov     rcx, r13; this
0x180027b9f  mov     rdx, [rbp+0B0h+var_128]; void *
0x180027ba3  mov     dword ptr [rsp+1B0h+var_188], edi; int
0x180027ba7  mov     [rsp+1B0h+var_190], rax; struct _GUID *
0x180027bac  call    ?BuildSecurityDescriptorForRoleSet@CSecurityAdmin2@@QEAAJPEAX0PEAPEAXPEAU_GUID@@H@Z; CSecurityAdmin2::BuildSecurityDescriptorForRoleSet(void *,void *,void * *,_GUID *,int)
0x180027bb1  xor     edi, edi
0x180027bb3  mov     ebx, eax
0x180027bb5  test    eax, eax
0x180027bb7  js      loc_180027FA9
0x180027bbd  mov     rcx, [rsp+1B0h+var_150]
0x180027bc2  mov     rax, [rcx]
0x180027bc5  mov     rax, [rax+80h]
0x180027bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bd1  mov     ebx, eax
0x180027bd3  test    eax, eax
0x180027bd5  js      loc_180027FA9
0x180027bdb  test    r14, r14
0x180027bde  jz      loc_180027DD0
0x180027be4  mov     rcx, [rsp+1B0h+var_150]
0x180027be9  lea     rdx, [rbp+0B0h+var_128]
0x180027bed  mov     [rbp+0B0h+var_128], rdi
0x180027bf1  xor     r9d, r9d
0x180027bf4  mov     [rsp+1B0h+var_190], rdx
0x180027bf9  xor     r8d, r8d
0x180027bfc  lea     edx, [rdi+9]
0x180027bff  mov     rax, [rcx]
0x180027c02  mov     rax, [rax+40h]
0x180027c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c0b  test    eax, eax
0x180027c0d  js      loc_180027DD0
0x180027c13  mov     rax, [rbp+0B0h+var_108]
0x180027c17  lea     ecx, [rdi+10h]
0x180027c1a  mov     [rbp+0B0h+var_C8], rax
0x180027c1e  lea     edx, [rdi+48h]
0x180027c21  mov     rax, [rbp+0B0h+var_110]
0x180027c25  lea     r9, tidCOMSERVICES_CLASSITFDISPID; struct _GUID *
0x180027c2c  mov     [rbp+0B0h+var_B0], rax
0x180027c30  mov     rax, [rbp+0B0h+var_128]
0x180027c34  mov     [rbp+0B0h+var_80], rax
0x180027c38  lea     eax, [rdi+13h]
0x180027c3b  mov     [rbp+0B0h+var_70], eax
0x180027c3e  mov     [rbp+0B0h+var_58], eax
0x180027c41  lea     rax, [rsp+1B0h+var_148]
0x180027c46  mov     [rsp+1B0h+var_170], rax; void **
0x180027c4b  lea     rax, [rbp+0B0h+var_E0]
0x180027c4f  mov     [rbp+0B0h+var_CC], ecx
0x180027c52  mov     [rbp+0B0h+var_B4], ecx
0x180027c55  mov     [rbp+0B0h+var_9C], ecx
0x180027c58  mov     [rbp+0B0h+var_84], ecx
0x180027c5b  lea     ecx, [rdi+4]; this
0x180027c5e  mov     dword ptr [rsp+1B0h+var_178], 20000h; unsigned int
0x180027c66  mov     [rbp+0B0h+var_D0], edx
0x180027c69  mov     [rbp+0B0h+var_B8], edx
0x180027c6c  mov     [rbp+0B0h+var_A0], edx
0x180027c6f  mov     [rbp+0B0h+var_88], edx
0x180027c72  mov     rdx, [r13+30h]; struct ISimpleTableDispenser *
0x180027c76  mov     [rsp+1B0h+var_188], 6; void *
0x180027c7f  mov     [rsp+1B0h+var_190], rax; void *
0x180027c84  mov     [rbp+0B0h+var_E0], r12
0x180027c88  mov     [rbp+0B0h+var_D8], rdi
0x180027c8c  mov     [rbp+0B0h+var_C0], edi
0x180027c8f  mov     [rbp+0B0h+var_BC], 1
0x180027c96  mov     [rbp+0B0h+var_A8], edi
0x180027c99  mov     [rbp+0B0h+var_A4], 2
0x180027ca0  mov     [rbp+0B0h+var_98], rsi
0x180027ca4  mov     [rbp+0B0h+var_90], edi
0x180027ca7  mov     [rbp+0B0h+var_8C], 3
0x180027cae  mov     [rbp+0B0h+var_78], edi
0x180027cb1  mov     [rbp+0B0h+var_74], ecx
0x180027cb4  mov     [rbp+0B0h+var_6C], ecx
0x180027cb7  mov     [rbp+0B0h+var_68], r15
0x180027cbb  mov     [rbp+0B0h+var_60], edi
0x180027cbe  mov     [rbp+0B0h+var_5C], 5
0x180027cc5  mov     [rbp+0B0h+var_54], ecx
0x180027cc8  mov     [rsp+1B0h+var_148], rdi
0x180027ccd  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180027cd2  test    eax, eax
0x180027cd4  js      loc_180027DBA
0x180027cda  mov     rcx, [rsp+1B0h+var_148]
0x180027cdf  mov     rax, [rcx]
0x180027ce2  mov     rax, [rax+18h]
0x180027ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ceb  test    eax, eax
0x180027ced  js      loc_180027DBA
0x180027cf3  mov     rcx, [rsp+1B0h+var_148]
0x180027cf8  xor     edx, edx
0x180027cfa  mov     rax, [rcx]
0x180027cfd  mov     rax, [rax+30h]
0x180027d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d06  test    eax, eax
0x180027d08  js      loc_180027DBA
0x180027d0e  mov     rcx, [rsp+1B0h+var_148]
0x180027d13  mov     rax, [rcx]
0x180027d16  mov     rax, [rax+80h]
0x180027d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d22  mov     ebx, eax
0x180027d24  test    eax, eax
0x180027d26  js      short loc_180027D92
0x180027d28  mov     rax, [rsp+1B0h+var_148]
0x180027d2d  mov     rbx, [rsp+1B0h+ObjectDescriptor]
0x180027d32  mov     rcx, [rax]
0x180027d35  mov     rdi, [rcx+0A0h]
0x180027d3c  mov     rcx, rbx; pSecurityDescriptor
0x180027d3f  call    cs:__imp_GetSecurityDescriptorLength
0x180027d45  mov     rcx, [rsp+1B0h+var_148]
0x180027d4a  mov     r9, rbx
0x180027d4d  mov     r8d, eax
0x180027d50  mov     edx, 6
0x180027d55  mov     rax, rdi
0x180027d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d5d  xor     edi, edi
0x180027d5f  mov     ebx, eax
0x180027d61  test    eax, eax
0x180027d63  js      short loc_180027D92
0x180027d65  mov     rcx, [rsp+1B0h+var_148]
0x180027d6a  mov     rax, [rcx]
0x180027d6d  mov     rax, [rax+90h]
0x180027d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d79  mov     ebx, eax
0x180027d7b  test    eax, eax
0x180027d7d  js      short loc_180027D92
0x180027d7f  mov     rcx, [rsp+1B0h+var_148]
0x180027d84  mov     rax, [rcx]
0x180027d87  mov     rax, [rax+60h]
0x180027d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d90  mov     ebx, eax
0x180027d92  mov     rcx, [rsp+1B0h+var_148]
0x180027d97  test    rcx, rcx
0x180027d9a  jz      short loc_180027DB0
0x180027d9c  mov     rax, [rcx]
0x180027d9f  mov     rax, [rax+10h]
0x180027da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027da8  mov     rcx, rdi
0x180027dab  mov     [rsp+1B0h+var_148], rcx
0x180027db0  test    ebx, ebx
0x180027db2  js      loc_180027FA9
0x180027db8  jmp     short loc_180027DBF
0x180027dba  mov     rcx, [rsp+1B0h+var_148]
0x180027dbf  test    rcx, rcx
0x180027dc2  jz      short loc_180027DD0
0x180027dc4  mov     rax, [rcx]
0x180027dc7  mov     rax, [rax+10h]
0x180027dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dd0  mov     rax, [rsp+1B0h+var_150]
0x180027dd5  mov     rbx, [rsp+1B0h+ObjectDescriptor]
0x180027dda  mov     rcx, [rax]
0x180027ddd  mov     rdi, [rcx+0A0h]
0x180027de4  mov     rcx, rbx; pSecurityDescriptor
0x180027de7  call    cs:__imp_GetSecurityDescriptorLength
0x180027ded  mov     edx, [rsp+1B0h+var_140]
0x180027df1  mov     r9, rbx
0x180027df4  mov     rcx, [rsp+1B0h+var_150]
0x180027df9  mov     r8d, eax
0x180027dfc  mov     rax, rdi
0x180027dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e04  xor     edi, edi
0x180027e06  mov     ebx, eax
0x180027e08  test    eax, eax
0x180027e0a  js      loc_180027FA9
0x180027e10  mov     rcx, [rsp+1B0h+var_150]
0x180027e15  mov     rax, [rcx]
0x180027e18  mov     rax, [rax+90h]
0x180027e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e24  mov     ebx, eax
0x180027e26  test    eax, eax
0x180027e28  js      loc_180027FA9
0x180027e2e  mov     rcx, [rsp+1B0h+var_150]
0x180027e33  mov     rax, [rcx]
0x180027e36  mov     rax, [rax+60h]
0x180027e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e3f  mov     ebx, eax
0x180027e41  test    eax, eax
0x180027e43  js      loc_180027FA9
0x180027e49  mov     rcx, [rsp+1B0h+var_150]
0x180027e4e  mov     [rbp+0B0h+var_100], rdi
0x180027e52  mov     [rbp+0B0h+var_12C], edi
0x180027e55  test    rcx, rcx
0x180027e58  jz      short loc_180027E6D
0x180027e5a  mov     rax, [rcx]
0x180027e5d  mov     rax, [rax+10h]
0x180027e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e66  mov     ecx, edi
0x180027e68  mov     [rsp+1B0h+var_150], rcx
0x180027e6d  test    r14, r14
0x180027e70  jnz     loc_180027FAE
0x180027e76  mov     r14, [rbp+0B0h+var_110]
0x180027e7a  lea     rax, [rsp+1B0h+var_13C]
0x180027e7f  mov     [rsp+1B0h+var_168], rax; unsigned int *
0x180027e84  mov     r9, r14; struct _GUID *
0x180027e87  lea     rax, [rbp+0B0h+var_F0]
0x180027e8b  mov     rdx, r12; struct _GUID *
0x180027e8e  mov     [rsp+1B0h+var_170], rax; struct _GUID *
0x180027e93  mov     rcx, r13; this
0x180027e96  lea     rax, [rsp+1B0h+var_150]
0x180027e9b  mov     [rsp+1B0h+var_178], rax; struct ISimpleTableWrite **
0x180027ea0  mov     [rsp+1B0h+var_180], r15; unsigned int *
0x180027ea5  mov     [rsp+1B0h+var_188], rdi; unsigned int *
0x180027eaa  mov     rdi, [rbp+0B0h+var_108]
0x180027eae  mov     r8, rdi; struct _GUID *
0x180027eb1  mov     [rsp+1B0h+var_190], rsi; struct _GUID *
0x180027eb6  call    ?GetSubTable@CSecurityAdmin2@@QEAAJPEAU_GUID@@000PEAK1PEAPEAUISimpleTableWrite@@01@Z; CSecurityAdmin2::GetSubTable(_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,ISimpleTableWrite * *,_GUID *,ulong *)
0x180027ebb  mov     ebx, eax
0x180027ebd  test    eax, eax
0x180027ebf  js      loc_180027FA9
0x180027ec5  mov     rcx, [rsp+1B0h+var_150]
0x180027eca  mov     rax, [rcx]
  ... truncated ...
```
