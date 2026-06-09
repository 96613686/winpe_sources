# CSecurityAdmin2::RecursiveUpdateNode(_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,void *,int,int)

- ea: `0x18003541c`
- end: `0x180035a04`
- name: `?RecursiveUpdateNode@CSecurityAdmin2@@QEAAJPEAU_GUID@@000PEAK1PEAXHH@Z`
- size: `1512`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this, struct _GUID *, struct _GUID *, struct _GUID *, struct _GUID *, unsigned int *, unsigned int *, void *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18003541c`
- `0x180035a0c`

## callees

- `0x180033d68`
- `0x18003496c`
- `0x180035060`
- `0x180035290`
- `0x18003541c`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003554c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003554c`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800359d5`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800359d5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003573f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800357e7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003573f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800357e7`

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
0x18003541c  push    rbp
0x18003541e  push    rbx
0x18003541f  push    rsi
0x180035420  push    rdi
0x180035421  push    r12
0x180035423  push    r13
0x180035425  push    r14
0x180035427  push    r15
0x180035429  lea     rbp, [rsp-78h]
0x18003542e  sub     rsp, 178h
0x180035435  mov     rax, cs:__security_cookie
0x18003543c  xor     rax, rsp
0x18003543f  mov     [rbp+0B0h+var_50], rax
0x180035443  mov     rax, [rbp+0B0h+arg_38]
0x18003544a  mov     r12, rdx
0x18003544d  mov     rsi, [rbp+0B0h+arg_20]
0x180035454  mov     r13, rcx
0x180035457  mov     r14, [rbp+0B0h+arg_28]
0x18003545e  mov     r15, [rbp+0B0h+arg_30]
0x180035465  mov     [rbp+0B0h+var_128], rax
0x180035469  xor     eax, eax
0x18003546b  mov     [rbp+0B0h+var_110], r9
0x18003546f  mov     [rbp+0B0h+var_108], r8
0x180035473  test    rdx, rdx
0x180035476  jz      loc_1800359DF
0x18003547c  test    r14, r14
0x18003547f  jz      short loc_18003548A
0x180035481  test    rsi, rsi
0x180035484  jz      loc_1800359DF
0x18003548a  test    r15, r15
0x18003548d  jz      loc_1800359DF
0x180035493  cmp     [rbp+0B0h+arg_40], eax
0x180035499  xorps   xmm0, xmm0
0x18003549c  mov     [rsp+1B0h+var_150], rax
0x1800354a1  mov     edi, 1
0x1800354a6  cmovz   edi, [rbp+0B0h+arg_48]
0x1800354ad  mov     [rsp+1B0h+var_140], eax
0x1800354b1  mov     dword ptr [rsp+1B0h+var_148], eax
0x1800354b5  mov     [rsp+1B0h+var_13C], eax
0x1800354b9  mov     [rbp+0B0h+var_130], eax
0x1800354bc  mov     [rbp+0B0h+pSecurityDescriptor], rax
0x1800354c0  mov     [rsp+1B0h+ObjectDescriptor], rax
0x1800354c5  mov     [rbp+0B0h+var_118], rax
0x1800354c9  mov     [rbp+0B0h+var_F8], rax
0x1800354cd  lea     rax, [rsp+1B0h+var_148]
0x1800354d2  mov     [rsp+1B0h+var_160], rax; unsigned int *
0x1800354d7  lea     rax, [rsp+1B0h+var_140]
0x1800354dc  mov     [rsp+1B0h+var_168], rax; unsigned int *
0x1800354e1  lea     rax, [rbp+0B0h+var_F0]
0x1800354e5  mov     [rsp+1B0h+var_170], rax; struct _GUID *
0x1800354ea  lea     rax, [rsp+1B0h+var_150]
0x1800354ef  mov     [rsp+1B0h+var_178], rax; struct ISimpleTableWrite **
0x1800354f4  mov     [rsp+1B0h+var_180], r15; unsigned int
0x1800354f9  mov     [rsp+1B0h+var_188], r14; unsigned int *
0x1800354fe  mov     [rsp+1B0h+var_190], rsi; struct _GUID *
0x180035503  movups  xmmword ptr [rbp+0B0h+var_F0.Data1], xmm0
0x180035507  call    ?GetNodeTable@CSecurityAdmin2@@QEAAJPEAU_GUID@@000PEAK1PEAPEAUISimpleTableWrite@@011@Z; CSecurityAdmin2::GetNodeTable(_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,ISimpleTableWrite * *,_GUID *,ulong *,ulong *)
0x18003550c  mov     ebx, eax
0x18003550e  test    eax, eax
0x180035510  js      loc_1800359A9
0x180035516  mov     rcx, [rsp+1B0h+var_150]
0x18003551b  lea     rdx, [rbp+0B0h+pSecurityDescriptor]
0x18003551f  mov     [rsp+1B0h+var_190], rdx
0x180035524  lea     r8, [rbp+0B0h+var_130]
0x180035528  mov     edx, [rsp+1B0h+var_140]
0x18003552c  xor     r9d, r9d
0x18003552f  mov     rax, [rcx]
0x180035532  mov     rax, [rax+40h]
0x180035536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003553b  test    eax, eax
0x18003553d  js      loc_1800359E4
0x180035543  mov     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180035547  test    rcx, rcx
0x18003554a  jz      short loc_180035560
0x18003554c  call    cs:__imp_IsValidSecurityDescriptor
0x180035552  test    eax, eax
0x180035554  jnz     short loc_180035560
0x180035556  mov     ebx, 8000FFFFh
0x18003555b  jmp     loc_1800359A9
0x180035560  mov     rcx, [rsp+1B0h+var_150]
0x180035565  lea     rdx, [rbp+0B0h+var_118]
0x180035569  mov     [rsp+1B0h+var_190], rdx
0x18003556e  lea     r8, [rbp+0B0h+var_130]
0x180035572  mov     edx, dword ptr [rsp+1B0h+var_148]
0x180035576  xor     r9d, r9d
0x180035579  mov     rax, [rcx]
0x18003557c  mov     rax, [rax+40h]
0x180035580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035585  mov     ebx, eax
0x180035587  test    eax, eax
0x180035589  js      loc_1800359A9
0x18003558f  mov     rax, [rbp+0B0h+var_118]
0x180035593  lea     r9, [rsp+1B0h+ObjectDescriptor]; void **
0x180035598  mov     r8, [rbp+0B0h+pSecurityDescriptor]; void *
0x18003559c  mov     rcx, r13; this
0x18003559f  mov     rdx, [rbp+0B0h+var_128]; void *
0x1800355a3  mov     dword ptr [rsp+1B0h+var_188], edi; int
0x1800355a7  mov     [rsp+1B0h+var_190], rax; struct _GUID *
0x1800355ac  call    ?BuildSecurityDescriptorForRoleSet@CSecurityAdmin2@@QEAAJPEAX0PEAPEAXPEAU_GUID@@H@Z; CSecurityAdmin2::BuildSecurityDescriptorForRoleSet(void *,void *,void * *,_GUID *,int)
0x1800355b1  xor     edi, edi
0x1800355b3  mov     ebx, eax
0x1800355b5  test    eax, eax
0x1800355b7  js      loc_1800359A9
0x1800355bd  mov     rcx, [rsp+1B0h+var_150]
0x1800355c2  mov     rax, [rcx]
0x1800355c5  mov     rax, [rax+80h]
0x1800355cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355d1  mov     ebx, eax
0x1800355d3  test    eax, eax
0x1800355d5  js      loc_1800359A9
0x1800355db  test    r14, r14
0x1800355de  jz      loc_1800357D0
0x1800355e4  mov     rcx, [rsp+1B0h+var_150]
0x1800355e9  lea     rdx, [rbp+0B0h+var_128]
0x1800355ed  mov     [rbp+0B0h+var_128], rdi
0x1800355f1  xor     r9d, r9d
0x1800355f4  mov     [rsp+1B0h+var_190], rdx
0x1800355f9  xor     r8d, r8d
0x1800355fc  lea     edx, [rdi+9]
0x1800355ff  mov     rax, [rcx]
0x180035602  mov     rax, [rax+40h]
0x180035606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003560b  test    eax, eax
0x18003560d  js      loc_1800357D0
0x180035613  mov     rax, [rbp+0B0h+var_108]
0x180035617  lea     ecx, [rdi+10h]
0x18003561a  mov     [rbp+0B0h+var_C8], rax
0x18003561e  lea     edx, [rdi+48h]
0x180035621  mov     rax, [rbp+0B0h+var_110]
0x180035625  lea     r9, tidCOMSERVICES_CLASSITFDISPID; struct _GUID *
0x18003562c  mov     [rbp+0B0h+var_B0], rax
0x180035630  mov     rax, [rbp+0B0h+var_128]
0x180035634  mov     [rbp+0B0h+var_80], rax
0x180035638  lea     eax, [rdi+13h]
0x18003563b  mov     [rbp+0B0h+var_70], eax
0x18003563e  mov     [rbp+0B0h+var_58], eax
0x180035641  lea     rax, [rsp+1B0h+var_148]
0x180035646  mov     [rsp+1B0h+var_170], rax; void **
0x18003564b  lea     rax, [rbp+0B0h+var_E0]
0x18003564f  mov     [rbp+0B0h+var_CC], ecx
0x180035652  mov     [rbp+0B0h+var_B4], ecx
0x180035655  mov     [rbp+0B0h+var_9C], ecx
0x180035658  mov     [rbp+0B0h+var_84], ecx
0x18003565b  lea     ecx, [rdi+4]; this
0x18003565e  mov     dword ptr [rsp+1B0h+var_178], 20000h; unsigned int
0x180035666  mov     [rbp+0B0h+var_D0], edx
0x180035669  mov     [rbp+0B0h+var_B8], edx
0x18003566c  mov     [rbp+0B0h+var_A0], edx
0x18003566f  mov     [rbp+0B0h+var_88], edx
0x180035672  mov     rdx, [r13+30h]; struct ISimpleTableDispenser *
0x180035676  mov     [rsp+1B0h+var_188], 6; void *
0x18003567f  mov     [rsp+1B0h+var_190], rax; void *
0x180035684  mov     [rbp+0B0h+var_E0], r12
0x180035688  mov     [rbp+0B0h+var_D8], rdi
0x18003568c  mov     [rbp+0B0h+var_C0], edi
0x18003568f  mov     [rbp+0B0h+var_BC], 1
0x180035696  mov     [rbp+0B0h+var_A8], edi
0x180035699  mov     [rbp+0B0h+var_A4], 2
0x1800356a0  mov     [rbp+0B0h+var_98], rsi
0x1800356a4  mov     [rbp+0B0h+var_90], edi
0x1800356a7  mov     [rbp+0B0h+var_8C], 3
0x1800356ae  mov     [rbp+0B0h+var_78], edi
0x1800356b1  mov     [rbp+0B0h+var_74], ecx
0x1800356b4  mov     [rbp+0B0h+var_6C], ecx
0x1800356b7  mov     [rbp+0B0h+var_68], r15
0x1800356bb  mov     [rbp+0B0h+var_60], edi
0x1800356be  mov     [rbp+0B0h+var_5C], 5
0x1800356c5  mov     [rbp+0B0h+var_54], ecx
0x1800356c8  mov     [rsp+1B0h+var_148], rdi
0x1800356cd  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x1800356d2  test    eax, eax
0x1800356d4  js      loc_1800357BA
0x1800356da  mov     rcx, [rsp+1B0h+var_148]
0x1800356df  mov     rax, [rcx]
0x1800356e2  mov     rax, [rax+18h]
0x1800356e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356eb  test    eax, eax
0x1800356ed  js      loc_1800357BA
0x1800356f3  mov     rcx, [rsp+1B0h+var_148]
0x1800356f8  xor     edx, edx
0x1800356fa  mov     rax, [rcx]
0x1800356fd  mov     rax, [rax+30h]
0x180035701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035706  test    eax, eax
0x180035708  js      loc_1800357BA
0x18003570e  mov     rcx, [rsp+1B0h+var_148]
0x180035713  mov     rax, [rcx]
0x180035716  mov     rax, [rax+80h]
0x18003571d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035722  mov     ebx, eax
0x180035724  test    eax, eax
0x180035726  js      short loc_180035792
0x180035728  mov     rax, [rsp+1B0h+var_148]
0x18003572d  mov     rbx, [rsp+1B0h+ObjectDescriptor]
0x180035732  mov     rcx, [rax]
0x180035735  mov     rdi, [rcx+0A0h]
0x18003573c  mov     rcx, rbx; pSecurityDescriptor
0x18003573f  call    cs:__imp_GetSecurityDescriptorLength
0x180035745  mov     rcx, [rsp+1B0h+var_148]
0x18003574a  mov     r9, rbx
0x18003574d  mov     r8d, eax
0x180035750  mov     edx, 6
0x180035755  mov     rax, rdi
0x180035758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003575d  xor     edi, edi
0x18003575f  mov     ebx, eax
0x180035761  test    eax, eax
0x180035763  js      short loc_180035792
0x180035765  mov     rcx, [rsp+1B0h+var_148]
0x18003576a  mov     rax, [rcx]
0x18003576d  mov     rax, [rax+90h]
0x180035774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035779  mov     ebx, eax
0x18003577b  test    eax, eax
0x18003577d  js      short loc_180035792
0x18003577f  mov     rcx, [rsp+1B0h+var_148]
0x180035784  mov     rax, [rcx]
0x180035787  mov     rax, [rax+60h]
0x18003578b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035790  mov     ebx, eax
0x180035792  mov     rcx, [rsp+1B0h+var_148]
0x180035797  test    rcx, rcx
0x18003579a  jz      short loc_1800357B0
0x18003579c  mov     rax, [rcx]
0x18003579f  mov     rax, [rax+10h]
0x1800357a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357a8  mov     rcx, rdi
0x1800357ab  mov     [rsp+1B0h+var_148], rcx
0x1800357b0  test    ebx, ebx
0x1800357b2  js      loc_1800359A9
0x1800357b8  jmp     short loc_1800357BF
0x1800357ba  mov     rcx, [rsp+1B0h+var_148]
0x1800357bf  test    rcx, rcx
0x1800357c2  jz      short loc_1800357D0
0x1800357c4  mov     rax, [rcx]
0x1800357c7  mov     rax, [rax+10h]
0x1800357cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357d0  mov     rax, [rsp+1B0h+var_150]
0x1800357d5  mov     rbx, [rsp+1B0h+ObjectDescriptor]
0x1800357da  mov     rcx, [rax]
0x1800357dd  mov     rdi, [rcx+0A0h]
0x1800357e4  mov     rcx, rbx; pSecurityDescriptor
0x1800357e7  call    cs:__imp_GetSecurityDescriptorLength
0x1800357ed  mov     edx, [rsp+1B0h+var_140]
0x1800357f1  mov     r9, rbx
0x1800357f4  mov     rcx, [rsp+1B0h+var_150]
0x1800357f9  mov     r8d, eax
0x1800357fc  mov     rax, rdi
0x1800357ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035804  xor     edi, edi
0x180035806  mov     ebx, eax
0x180035808  test    eax, eax
0x18003580a  js      loc_1800359A9
0x180035810  mov     rcx, [rsp+1B0h+var_150]
0x180035815  mov     rax, [rcx]
0x180035818  mov     rax, [rax+90h]
0x18003581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035824  mov     ebx, eax
0x180035826  test    eax, eax
0x180035828  js      loc_1800359A9
0x18003582e  mov     rcx, [rsp+1B0h+var_150]
0x180035833  mov     rax, [rcx]
0x180035836  mov     rax, [rax+60h]
0x18003583a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003583f  mov     ebx, eax
0x180035841  test    eax, eax
0x180035843  js      loc_1800359A9
0x180035849  mov     rcx, [rsp+1B0h+var_150]
0x18003584e  mov     [rbp+0B0h+var_100], rdi
0x180035852  mov     [rbp+0B0h+var_12C], edi
0x180035855  test    rcx, rcx
0x180035858  jz      short loc_18003586D
0x18003585a  mov     rax, [rcx]
0x18003585d  mov     rax, [rax+10h]
0x180035861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035866  mov     ecx, edi
0x180035868  mov     [rsp+1B0h+var_150], rcx
0x18003586d  test    r14, r14
0x180035870  jnz     loc_1800359AE
0x180035876  mov     r14, [rbp+0B0h+var_110]
0x18003587a  lea     rax, [rsp+1B0h+var_13C]
0x18003587f  mov     [rsp+1B0h+var_168], rax; unsigned int *
0x180035884  mov     r9, r14; struct _GUID *
0x180035887  lea     rax, [rbp+0B0h+var_F0]
0x18003588b  mov     rdx, r12; struct _GUID *
0x18003588e  mov     [rsp+1B0h+var_170], rax; struct _GUID *
0x180035893  mov     rcx, r13; this
0x180035896  lea     rax, [rsp+1B0h+var_150]
0x18003589b  mov     [rsp+1B0h+var_178], rax; struct ISimpleTableWrite **
0x1800358a0  mov     [rsp+1B0h+var_180], r15; unsigned int *
0x1800358a5  mov     [rsp+1B0h+var_188], rdi; unsigned int *
0x1800358aa  mov     rdi, [rbp+0B0h+var_108]
0x1800358ae  mov     r8, rdi; struct _GUID *
0x1800358b1  mov     [rsp+1B0h+var_190], rsi; struct _GUID *
0x1800358b6  call    ?GetSubTable@CSecurityAdmin2@@QEAAJPEAU_GUID@@000PEAK1PEAPEAUISimpleTableWrite@@01@Z; CSecurityAdmin2::GetSubTable(_GUID *,_GUID *,_GUID *,_GUID *,ulong *,ulong *,ISimpleTableWrite * *,_GUID *,ulong *)
0x1800358bb  mov     ebx, eax
0x1800358bd  test    eax, eax
0x1800358bf  js      loc_1800359A9
0x1800358c5  mov     rcx, [rsp+1B0h+var_150]
0x1800358ca  mov     rax, [rcx]
  ... truncated ...
```
