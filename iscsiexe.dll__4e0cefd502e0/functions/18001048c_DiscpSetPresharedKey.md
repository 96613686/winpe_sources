# DiscpSetPresharedKey

- ea: `0x18001048c`
- end: `0x1800106e6`
- name: `DiscpSetPresharedKey`
- size: `602`
- prototype: `__int64 __fastcall(__int64, int, __int64, char, size_t, void *, size_t, void *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003e50`
- `0x180008e84`
- `0x18000fe70`

## callees

- `0x18000ecdc`
- `0x18000edbc`
- `0x18000f4a8`
- `0x18000fbdc`
- `0x18001048c`
- `0x1800106ec`
- `0x180010770`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180010533`
- `ISCSIUM!DiscpFreeMemory` at `0x1800105f2`
- `ISCSIUM!DiscpFreeMemory` at `0x180010613`
- `ISCSIUM!DiscpFreeMemory` at `0x1800106c6`
- `ISCSIUM!DiscpFreeMemory` at `0x180010533`
- `ISCSIUM!DiscpFreeMemory` at `0x1800105f2`
- `ISCSIUM!DiscpFreeMemory` at `0x180010613`
- `ISCSIUM!DiscpFreeMemory` at `0x1800106c6`
- `WMICLNT!WmiCloseBlock` at `0x18001061d`
- `WMICLNT!WmiCloseBlock` at `0x1800106bc`
- `WMICLNT!WmiCloseBlock` at `0x18001061d`
- `WMICLNT!WmiCloseBlock` at `0x1800106bc`
- `WMICLNT!WmiOpenBlock` at `0x180010686`
- `WMICLNT!WmiOpenBlock` at `0x180010686`

## pseudocode

```c
__int64 __fastcall DiscpSetPresharedKey(
        __int64 a1,
        int a2,
        __int64 a3,
        char a4,
        size_t a5,
        void *a6,
        size_t a7,
        void *a8,
        int a9)
{
  char v10; // al
  int v11; // r10d
  __int64 v13; // rsi
  void *v14; // r15
  int v15; // r12d
  void *Src; // r13
  unsigned int v17; // ebx
  int v18; // esi
  int v19; // edx
  int v20; // edx
  int InitiatorsSupportingSecurity; // ebx
  __int64 v22; // r14
  __int64 v23; // r15
  __int64 v24; // rdi
  int v25; // esi
  int v26; // eax
  size_t Size; // [rsp+28h] [rbp-48h]
  size_t v29; // [rsp+38h] [rbp-38h]
  __int64 v30; // [rsp+50h] [rbp-20h] BYREF
  int v31[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v32; // [rsp+60h] [rbp-10h] BYREF
  __int64 v33; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v34; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+50h]
  char v36; // [rsp+C8h] [rbp+58h]

  v36 = a4;
  v35 = a3;
  v10 = a4;
  v11 = a3;
  v30 = 0;
  *(_QWORD *)v31 = 0;
  v33 = 0;
  v34 = 0;
  v32 = 0;
  if ( a1 )
    v13 = *(_QWORD *)(a1 + 40);
  else
    v13 = 0;
  v14 = a8;
  v15 = a7;
  Src = a6;
  if ( (_BYTE)a9 )
  {
    v17 = DiscpBuildPsKeyAuthInfo(a3, a4, a5, a6, a7, a8, &v32);
    if ( v17 )
      return v17;
    v17 = DiscpPersistAuthInfo(v13, a2, v32);
    DiscpFreeMemory(v32);
    if ( v17 )
      return v17;
    v10 = v36;
    v11 = v35;
  }
  v18 = a5;
  LODWORD(v29) = v15;
  a9 = 0;
  *(_QWORD *)v31 = 0;
  LODWORD(Size) = a5;
  v17 = DiscpBuildSetPresharedKeyIn((int)v31, (int)&a9, a2, v11, v10, Size, Src, v29, v14);
  if ( !v17 )
  {
    if ( a1 )
    {
      if ( (*(_BYTE *)(a1 + 20) & 2) != 0 )
      {
        LOBYTE(v19) = v36;
        v17 = DiscpSetPresharedKeyForSPD(v35, v19, v18, (_DWORD)Src, v15, (__int64)v14);
      }
      else
      {
        v17 = WmiOpenBlock(MSiSCSI_SecurityConfigOperations_GUID, 2684354560LL, &v30);
        if ( !v17 )
        {
          if ( (*(_BYTE *)(a1 + 36) & 1) != 0 )
            v17 = DiscpSetPresharedKeyForAdapter(v30, a1, *(_QWORD *)v31, (unsigned int)a9);
          else
            v17 = -268500945;
          WmiCloseBlock(v30);
        }
      }
    }
    else
    {
      InitiatorsSupportingSecurity = DiscpGetInitiatorsSupportingSecurity(&v30, &v34, &v33);
      if ( !InitiatorsSupportingSecurity )
      {
        v22 = 0;
        if ( v34 )
        {
          v23 = v33;
          do
          {
            v24 = *(_QWORD *)(v23 + 8 * v22);
            if ( (*(_BYTE *)(v24 + 36) & 1) != 0 )
              v25 = DiscpSetPresharedKeyForAdapter(v30, *(_QWORD *)(v23 + 8 * v22), *(_QWORD *)v31, (unsigned int)a9);
            else
              v25 = 0;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24 + 16), 0xFFFFFFFF) == 1 )
              DiscpFreeMemory(v24);
            if ( !v25 )
              v25 = InitiatorsSupportingSecurity;
            v22 = (unsigned int)(v22 + 1);
            InitiatorsSupportingSecurity = v25;
          }
          while ( (unsigned int)v22 < v34 );
          v14 = a8;
          v18 = a5;
        }
        DiscpFreeMemory(v33);
        WmiCloseBlock(v30);
      }
      LOBYTE(v20) = v36;
      v26 = DiscpSetPresharedKeyForSPD(v35, v20, v18, (_DWORD)Src, v15, (__int64)v14);
      if ( v26 )
        InitiatorsSupportingSecurity = v26;
      v17 = InitiatorsSupportingSecurity != 0 ? 0xAFFF002E : 0;
    }
    DiscpFreeMemory(*(_QWORD *)v31);
  }
  return v17;
}

```

## disassembly

```asm
0x18001048c  mov     [rsp-38h+arg_8], rbx
0x180010491  mov     [rsp-38h+arg_18], r9b
0x180010496  mov     [rsp-38h+arg_10], r8
0x18001049b  push    rbp
0x18001049c  push    rsi
0x18001049d  push    rdi
0x18001049e  push    r12
0x1800104a0  push    r13
0x1800104a2  push    r14
0x1800104a4  push    r15
0x1800104a6  mov     rbp, rsp
0x1800104a9  sub     rsp, 70h
0x1800104ad  mov     rdi, rcx
0x1800104b0  mov     al, r9b
0x1800104b3  xor     ecx, ecx
0x1800104b5  mov     r10, r8
0x1800104b8  mov     [rbp+var_20], rcx
0x1800104bc  mov     r14d, edx
0x1800104bf  mov     qword ptr [rbp+var_18], rcx
0x1800104c3  mov     [rbp+var_8], rcx
0x1800104c7  mov     [rbp+arg_0], ecx
0x1800104ca  mov     [rbp+var_10], rcx
0x1800104ce  test    rdi, rdi
0x1800104d1  jz      short loc_1800104D9
0x1800104d3  mov     rsi, [rdi+28h]
0x1800104d7  jmp     short loc_1800104DC
0x1800104d9  mov     rsi, rcx
0x1800104dc  mov     r15, [rbp+arg_38]
0x1800104e0  mov     r12d, dword ptr [rbp+arg_30]
0x1800104e4  mov     r13, [rbp+arg_28]
0x1800104e8  cmp     byte ptr [rbp+arg_40], cl
0x1800104ee  jz      short loc_18001054A
0x1800104f0  mov     r8d, dword ptr [rbp+arg_20]
0x1800104f4  lea     rcx, [rbp+var_10]
0x1800104f8  mov     [rsp+70h+Src], rcx
0x1800104fd  mov     r9, r13
0x180010500  mov     [rsp+70h+Size], r15
0x180010505  mov     rcx, r10
0x180010508  mov     dl, al
0x18001050a  mov     dword ptr [rsp+70h+var_50], r12d
0x18001050f  call    DiscpBuildPsKeyAuthInfo
0x180010514  mov     ebx, eax
0x180010516  test    eax, eax
0x180010518  jnz     loc_1800106CC
0x18001051e  mov     r8, [rbp+var_10]
0x180010522  mov     edx, r14d
0x180010525  mov     rcx, rsi
0x180010528  call    DiscpPersistAuthInfo
0x18001052d  mov     rcx, [rbp+var_10]
0x180010531  mov     ebx, eax
0x180010533  call    cs:__imp_DiscpFreeMemory
0x180010539  xor     ecx, ecx
0x18001053b  test    ebx, ebx
0x18001053d  jnz     loc_1800106CC
0x180010543  mov     al, [rbp+arg_18]
0x180010546  mov     r10, [rbp+arg_10]
0x18001054a  mov     esi, dword ptr [rbp+arg_20]
0x18001054d  lea     rdx, [rbp+arg_40]; int
0x180010554  mov     [rsp+70h+var_30], r15; void *
0x180010559  mov     r9, r10; int
0x18001055c  mov     dword ptr [rsp+70h+var_38], r12d; size_t
0x180010561  mov     r8d, r14d; int
0x180010564  mov     [rsp+70h+Src], r13; Src
0x180010569  mov     [rbp+arg_40], ecx
0x18001056f  mov     qword ptr [rbp+var_18], rcx
0x180010573  lea     rcx, [rbp+var_18]; int
0x180010577  mov     dword ptr [rsp+70h+Size], esi; Size
0x18001057b  mov     [rsp+70h+var_50], al; char
0x18001057f  call    DiscpBuildSetPresharedKeyIn
0x180010584  mov     ebx, eax
0x180010586  test    eax, eax
0x180010588  jnz     loc_1800106CC
0x18001058e  test    rdi, rdi
0x180010591  jnz     loc_180010650
0x180010597  lea     r8, [rbp+var_8]
0x18001059b  lea     rdx, [rbp+arg_0]
0x18001059f  lea     rcx, [rbp+var_20]
0x1800105a3  call    DiscpGetInitiatorsSupportingSecurity
0x1800105a8  mov     ebx, eax
0x1800105aa  test    eax, eax
0x1800105ac  jnz     short loc_180010623
0x1800105ae  xor     r14d, r14d
0x1800105b1  cmp     [rbp+arg_0], r14d
0x1800105b5  jbe     short loc_18001060F
0x1800105b7  mov     r15, [rbp+var_8]
0x1800105bb  mov     rdi, [r15+r14*8]
0x1800105bf  test    byte ptr [rdi+24h], 1
0x1800105c3  jz      short loc_1800105E0
0x1800105c5  mov     r9d, [rbp+arg_40]
0x1800105cc  mov     rdx, rdi
0x1800105cf  mov     r8, qword ptr [rbp+var_18]
0x1800105d3  mov     rcx, [rbp+var_20]
0x1800105d7  call    DiscpSetPresharedKeyForAdapter
0x1800105dc  mov     esi, eax
0x1800105de  jmp     short loc_1800105E2
0x1800105e0  xor     esi, esi
0x1800105e2  or      eax, 0FFFFFFFFh
0x1800105e5  lock xadd [rdi+10h], eax
0x1800105ea  cmp     eax, 1
0x1800105ed  jnz     short loc_1800105F8
0x1800105ef  mov     rcx, rdi
0x1800105f2  call    cs:__imp_DiscpFreeMemory
0x1800105f8  test    esi, esi
0x1800105fa  cmovz   esi, ebx
0x1800105fd  inc     r14d
0x180010600  mov     ebx, esi
0x180010602  cmp     r14d, [rbp+arg_0]
0x180010606  jb      short loc_1800105BB
0x180010608  mov     r15, [rbp+arg_38]
0x18001060c  mov     esi, dword ptr [rbp+arg_20]
0x18001060f  mov     rcx, [rbp+var_8]
0x180010613  call    cs:__imp_DiscpFreeMemory
0x180010619  mov     rcx, [rbp+var_20]
0x18001061d  call    cs:__imp_WmiCloseBlock
0x180010623  mov     dl, [rbp+arg_18]
0x180010626  mov     r9, r13
0x180010629  mov     rcx, [rbp+arg_10]
0x18001062d  mov     r8d, esi
0x180010630  mov     [rsp+70h+Size], r15
0x180010635  mov     dword ptr [rsp+70h+var_50], r12d
0x18001063a  call    DiscpSetPresharedKeyForSPD
0x18001063f  test    eax, eax
0x180010641  cmovnz  ebx, eax
0x180010644  neg     ebx
0x180010646  sbb     ebx, ebx
0x180010648  and     ebx, 0AFFF002Eh
0x18001064e  jmp     short loc_1800106C2
0x180010650  test    byte ptr [rdi+14h], 2
0x180010654  jz      short loc_180010676
0x180010656  mov     dl, [rbp+arg_18]
0x180010659  mov     r9, r13
0x18001065c  mov     rcx, [rbp+arg_10]
0x180010660  mov     r8d, esi
0x180010663  mov     [rsp+70h+Size], r15
0x180010668  mov     dword ptr [rsp+70h+var_50], r12d
0x18001066d  call    DiscpSetPresharedKeyForSPD
0x180010672  mov     ebx, eax
0x180010674  jmp     short loc_1800106C2
0x180010676  lea     r8, [rbp+var_20]
0x18001067a  mov     edx, 0A0000000h
0x18001067f  lea     rcx, MSiSCSI_SecurityConfigOperations_GUID
0x180010686  call    cs:__imp_WmiOpenBlock
0x18001068c  mov     ebx, eax
0x18001068e  test    eax, eax
0x180010690  jnz     short loc_1800106C2
0x180010692  test    byte ptr [rdi+24h], 1
0x180010696  jz      short loc_1800106B3
0x180010698  mov     r9d, [rbp+arg_40]
0x18001069f  mov     rdx, rdi
0x1800106a2  mov     r8, qword ptr [rbp+var_18]
0x1800106a6  mov     rcx, [rbp+var_20]
0x1800106aa  call    DiscpSetPresharedKeyForAdapter
0x1800106af  mov     ebx, eax
0x1800106b1  jmp     short loc_1800106B8
0x1800106b3  mov     ebx, 0EFFF002Fh
0x1800106b8  mov     rcx, [rbp+var_20]
0x1800106bc  call    cs:__imp_WmiCloseBlock
0x1800106c2  mov     rcx, qword ptr [rbp+var_18]
0x1800106c6  call    cs:__imp_DiscpFreeMemory
0x1800106cc  mov     eax, ebx
0x1800106ce  mov     rbx, [rsp+70h+arg_8]
0x1800106d6  add     rsp, 70h
0x1800106da  pop     r15
0x1800106dc  pop     r14
0x1800106de  pop     r13
0x1800106e0  pop     r12
0x1800106e2  pop     rdi
0x1800106e3  pop     rsi
0x1800106e4  pop     rbp
0x1800106e5  retn
```
