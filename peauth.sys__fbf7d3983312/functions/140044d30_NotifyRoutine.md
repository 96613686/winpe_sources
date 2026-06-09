# NotifyRoutine

- ea: `0x140044d30`
- end: `0x140045146`
- name: `NotifyRoutine`
- size: `1046`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001330`
- `0x1400013c4`
- `0x140025fd0`
- `0x140044c20`
- `0x140044d30`
- `0x14004519c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045090`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400450dd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045090`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400450dd`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140044d63`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140044d63`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400450b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400450fa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400450b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400450fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400450bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045106`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400450bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045106`
- `ntoskrnl!ObfDereferenceObject` at `0x140045125`
- `ntoskrnl!ObfDereferenceObject` at `0x140045125`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004507b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400450c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004507b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400450c8`
- `ntoskrnl!PsGetProcessProtection` at `0x140044d82`
- `ntoskrnl!PsGetProcessProtection` at `0x140044d82`

## pseudocode

```c
void __fastcall NotifyRoutine(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)
{
  __int64 v3; // r8
  unsigned __int64 v4; // r12
  unsigned __int64 v5; // r13
  unsigned int v6; // ebx
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r9
  unsigned int v11; // edi
  char v12; // si
  __int64 v13; // r14
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned __int64 v16; // r15
  __int64 v17; // rsi
  HANDLE v18; // r13
  signed __int64 v19; // r15
  unsigned __int64 v20; // r8
  __int64 v21; // rbx
  __int64 v22; // r14
  unsigned __int64 v23; // rdi
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rcx
  unsigned int v28; // [rsp+24h] [rbp-55h]
  signed __int64 v29; // [rsp+28h] [rbp-51h] BYREF
  __int64 (__fastcall **v30)(); // [rsp+30h] [rbp-49h] BYREF
  PEPROCESS Process; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-39h] BYREF
  __int64 v33; // [rsp+44h] [rbp-35h]
  int v34; // [rsp+4Ch] [rbp-2Dh]
  unsigned int v35; // [rsp+50h] [rbp-29h]
  unsigned int v36; // [rsp+54h] [rbp-25h]
  unsigned __int64 v37; // [rsp+58h] [rbp-21h]
  __int64 v38; // [rsp+60h] [rbp-19h]
  HANDLE v39; // [rsp+68h] [rbp-11h]
  __int64 v40; // [rsp+70h] [rbp-9h]
  _QWORD v41[11]; // [rsp+78h] [rbp-1h]

  v39 = ProcessId;
  Process = 0;
  if ( (PsLookupProcessByProcessId(ProcessId, &Process) & 0xC0000000) != 0xC0000000
    && (PsGetProcessProtection(Process) & 7) == 2 )
  {
    v40 = qword_14003A378;
    v3 = 0;
    v30 = off_140028080;
    v29 = 0;
    v4 = (unsigned __int64)qword_14003A378 >> 63;
    v28 = 0;
    do
    {
      v5 = qword_140037EC8[v3];
      v6 = 0;
      v7 = v5;
      v33 = 0;
      v8 = v5 >> 36;
      v9 = (v7 >> 6) & 0xFFFFFFF;
      v38 = v9;
      v32 = 0;
      v34 = 0;
      v10 = 0x140000000LL + v8;
      v37 = 0x140000000LL + v8;
      if ( (_DWORD)v4 )
      {
        sub_140001330(&v32, (unsigned int)v8, (unsigned int)v9);
        v11 = v36;
        if ( v36 >= v32 || (*(_DWORD *)(v33 + 4LL * v36) & 0xFFFFFFFu) >= v35 )
        {
          v12 = 0;
        }
        else
        {
          v6 = *(_DWORD *)(v33 + 4LL * v36);
          v11 = v36 + 1;
          v12 = 1;
        }
        v3 = v28;
        v10 = v37;
      }
      else
      {
        v11 = v36;
        v12 = 0;
      }
      v13 = 0;
      if ( (_DWORD)v9 )
      {
        do
        {
          if ( (_DWORD)v4 && v12 && (_DWORD)v13 + (_DWORD)v8 == (v6 & 0xFFFFFFF) )
          {
            v14 = v6 >> 28;
            if ( v6 >> 28 )
            {
              v15 = qword_14003A0C0 - 0x140000000LL;
              if ( v14 == 3 )
              {
                v16 = 4;
                LODWORD(v41[0]) = *(_DWORD *)(v13 + v10) + v15;
              }
              else if ( v14 == 10 )
              {
                v16 = 8;
                v41[0] = *(_QWORD *)(v13 + v10) + v15;
              }
              else
              {
                v16 = -1;
              }
              v17 = 0;
              do
              {
                LOBYTE(v3) = *((_BYTE *)v41 + v17);
                ((void (__fastcall *)(__int64 (__fastcall ***)(), signed __int64 *, __int64, unsigned __int64))v30[1])(
                  &v30,
                  &v29,
                  v3,
                  v10);
                v17 = (unsigned int)(v17 + 1);
              }
              while ( (unsigned int)v17 < v16 );
              LODWORD(v9) = v38;
            }
            else
            {
              LODWORD(v17) = 0;
            }
            v13 = (unsigned int)(v17 + v13);
            if ( v11 >= v32 || (*(_DWORD *)(v33 + 4LL * v11) & 0xFFFFFFFu) >= v35 )
            {
              v12 = 0;
            }
            else
            {
              v6 = *(_DWORD *)(v33 + 4LL * v11++);
              v12 = 1;
            }
          }
          else
          {
            LOBYTE(v3) = *(_BYTE *)(v13 + v10);
            ((void (__fastcall *)(__int64 (__fastcall ***)(), signed __int64 *, __int64))v30[1])(&v30, &v29, v3);
            v13 = (unsigned int)(v13 + 1);
          }
          v10 = v37;
        }
        while ( (unsigned int)v13 < (unsigned int)v9 );
        LODWORD(v3) = v28;
      }
      v3 = (unsigned int)(v3 + 1);
      v28 = v3;
    }
    while ( (unsigned int)v3 < 2 );
    v18 = v39;
    v19 = v40;
    v20 = 0x8000000000000000uLL;
    if ( (v29 | 0x8000000000000000uLL) == (v40 | 0x8000000000000000uLL) )
    {
      if ( (_DWORD)v4 )
      {
        v21 = 0;
        v29 = 0;
        do
        {
          v22 = 0;
          v23 = qword_140037EC8[v21];
          v24 = 0x140000000LL + (v23 >> 36);
          v25 = (v23 >> 6) & 0xFFFFFFF;
          if ( (_DWORD)v25 )
          {
            do
            {
              LOBYTE(v20) = *(_BYTE *)(v22 + v24);
              ((void (__fastcall *)(__int64 (__fastcall ***)(), signed __int64 *, unsigned __int64))v30[1])(
                &v30,
                &v29,
                v20);
              v22 = (unsigned int)(v22 + 1);
            }
            while ( (unsigned int)v22 < (unsigned int)v25 );
          }
          v21 = (unsigned int)(v21 + 1);
        }
        while ( (unsigned int)v21 < 2 );
        v29 &= ~0x8000000000000000uLL;
        _InterlockedCompareExchange64(&qword_14003A378, v29, v19);
      }
    }
    else
    {
      sub_1400013C4(2147483650LL, v29 | 0x8000000000000000uLL, 0x8000000000000000uLL, 0x3FFFFFFF);
    }
    if ( Create )
    {
      v26 = 1;
    }
    else
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&stru_14003A9C0, 1u);
      sub_140044C20(v18, 1);
      ExReleaseResourceLite(&stru_14003A9C0);
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&stru_14003A940, 1u);
      sub_140044C20(v18, 0);
      ExReleaseResourceLite(&stru_14003A940);
      KeLeaveCriticalRegion();
      v26 = 0;
    }
    sub_14004519C(v26, v18);
  }
  if ( Process )
    ObfDereferenceObject(Process);
}

```

## disassembly

```asm
0x140044d30  push    rbp
0x140044d32  push    rbx
0x140044d33  push    rsi
0x140044d34  push    rdi
0x140044d35  push    r12
0x140044d37  push    r13
0x140044d39  push    r14
0x140044d3b  push    r15
0x140044d3d  lea     rbp, [rsp-1Fh]
0x140044d42  sub     rsp, 98h
0x140044d49  mov     r13, rdx
0x140044d4c  mov     [rbp+57h+var_68], rdx
0x140044d50  mov     rcx, r13; ProcessId
0x140044d53  mov     [rbp+57h+var_B0], r8b
0x140044d57  lea     rdx, [rbp+57h+Process]; Process
0x140044d5b  mov     [rbp+57h+Process], 0
0x140044d63  call    cs:PsLookupProcessByProcessId
0x140044d6a  nop     dword ptr [rax+rax+00h]
0x140044d6f  mov     ecx, 0C0000000h
0x140044d74  and     eax, ecx
0x140044d76  cmp     eax, ecx
0x140044d78  jz      loc_14004511C
0x140044d7e  mov     rcx, [rbp+57h+Process]
0x140044d82  call    cs:PsGetProcessProtection
0x140044d89  nop     dword ptr [rax+rax+00h]
0x140044d8e  and     al, 7
0x140044d90  cmp     al, 2
0x140044d92  jnz     loc_14004511C
0x140044d98  mov     rcx, cs:qword_140037EC0
0x140044d9f  test    ecx, ecx
0x140044da1  jns     loc_14004506B
0x140044da7  mov     r15, cs:qword_14003A378
0x140044dae  lea     rax, off_140028080
0x140044db5  xor     edx, edx
0x140044db7  mov     [rbp+57h+var_60], r15
0x140044dbb  xor     r8d, r8d
0x140044dbe  mov     [rbp+57h+var_A0], rax
0x140044dc2  mov     r12, r15
0x140044dc5  mov     [rbp+57h+var_A8], rdx
0x140044dc9  shr     r12, 3Fh
0x140044dcd  lea     r10, cs:140000000h
0x140044dd4  mov     r9d, 3FFFFFFFh
0x140044dda  mov     [rbp+57h+var_AC], r8d
0x140044dde  test    r9d, ecx
0x140044de1  jbe     loc_140044FB2
0x140044de7  mov     r13, ds:rva qword_140037EC8[r10+r8*8]
0x140044def  xor     ebx, ebx
0x140044df1  mov     r15, r13
0x140044df4  mov     [rbp+57h+var_8C], 0
0x140044dfc  shr     r15, 6
0x140044e00  shr     r13, 24h
0x140044e04  and     r15d, 0FFFFFFFh
0x140044e0b  mov     [rbp+57h+var_70], r15
0x140044e0f  mov     [rbp+57h+var_90], 0
0x140044e16  mov     [rbp+57h+var_84], 0
0x140044e1d  lea     r9, [r10+r13]
0x140044e21  mov     [rbp+57h+var_78], r9
0x140044e25  test    r12d, r12d
0x140044e28  jz      short loc_140044E71
0x140044e2a  mov     r8d, r15d
0x140044e2d  lea     rcx, [rbp+57h+var_90]
0x140044e31  mov     edx, r13d
0x140044e34  call    sub_140001330
0x140044e39  mov     edi, [rbp+57h+var_7C]
0x140044e3c  cmp     edi, [rbp+57h+var_90]
0x140044e3f  jnb     short loc_140044E5D
0x140044e41  mov     rcx, [rbp+57h+var_8C]
0x140044e45  mov     ecx, [rcx+rdi*4]
0x140044e48  mov     eax, ecx
0x140044e4a  and     eax, 0FFFFFFFh
0x140044e4f  cmp     eax, [rbp+57h+var_80]
0x140044e52  jnb     short loc_140044E5D
0x140044e54  mov     ebx, ecx
0x140044e56  inc     edi
0x140044e58  mov     sil, 1
0x140044e5b  jmp     short loc_140044E60
0x140044e5d  xor     sil, sil
0x140044e60  mov     r8d, [rbp+57h+var_AC]
0x140044e64  lea     r10, cs:140000000h
0x140044e6b  mov     r9, [rbp+57h+var_78]
0x140044e6f  jmp     short loc_140044E77
0x140044e71  mov     edi, [rbp+57h+var_7C]
0x140044e74  xor     sil, sil
0x140044e77  xor     r14d, r14d
0x140044e7a  test    r15d, r15d
0x140044e7d  jz      loc_140044F76
0x140044e83  test    r12d, r12d
0x140044e86  jz      loc_140044F41
0x140044e8c  test    sil, sil
0x140044e8f  jz      loc_140044F41
0x140044e95  mov     eax, ebx
0x140044e97  lea     ecx, [r14+r13]
0x140044e9b  and     eax, 0FFFFFFFh
0x140044ea0  cmp     ecx, eax
0x140044ea2  jnz     loc_140044F41
0x140044ea8  mov     rcx, cs:qword_14003A0C0
0x140044eaf  mov     eax, ebx
0x140044eb1  shr     eax, 1Ch
0x140044eb4  test    eax, eax
0x140044eb6  jz      short loc_140044F14
0x140044eb8  sub     rcx, r10
0x140044ebb  cmp     eax, 3
0x140044ebe  jz      short loc_140044EDB
0x140044ec0  cmp     eax, 0Ah
0x140044ec3  jz      short loc_140044ECB
0x140044ec5  or      r15, 0FFFFFFFFFFFFFFFFh
0x140044ec9  jmp     short loc_140044EE8
0x140044ecb  add     rcx, [r14+r9]
0x140044ecf  mov     r15d, 8
0x140044ed5  mov     [rbp+57h+var_58], rcx
0x140044ed9  jmp     short loc_140044EE8
0x140044edb  add     ecx, [r14+r9]
0x140044edf  mov     r15d, 4
0x140044ee5  mov     dword ptr [rbp+57h+var_58], ecx
0x140044ee8  xor     esi, esi
0x140044eea  mov     rax, [rbp+57h+var_A0]
0x140044eee  lea     rdx, [rbp+57h+var_A8]
0x140044ef2  mov     r8b, byte ptr [rbp+rsi+57h+var_58]
0x140044ef7  lea     rcx, [rbp+57h+var_A0]
0x140044efb  mov     rax, [rax+8]
0x140044eff  call    cs:__guard_dispatch_icall_fptr
0x140044f05  inc     esi
0x140044f07  mov     eax, esi
0x140044f09  cmp     rax, r15
0x140044f0c  jb      short loc_140044EEA
0x140044f0e  mov     r15, [rbp+57h+var_70]
0x140044f12  jmp     short loc_140044F16
0x140044f14  xor     esi, esi
0x140044f16  add     r14d, esi
0x140044f19  cmp     edi, [rbp+57h+var_90]
0x140044f1c  jnb     short loc_140044F3C
0x140044f1e  mov     rcx, [rbp+57h+var_8C]
0x140044f22  mov     eax, edi
0x140044f24  mov     ecx, [rcx+rax*4]
0x140044f27  mov     eax, ecx
0x140044f29  and     eax, 0FFFFFFFh
0x140044f2e  cmp     eax, [rbp+57h+var_80]
0x140044f31  jnb     short loc_140044F3C
0x140044f33  mov     ebx, ecx
0x140044f35  inc     edi
0x140044f37  mov     sil, 1
0x140044f3a  jmp     short loc_140044F5E
0x140044f3c  xor     sil, sil
0x140044f3f  jmp     short loc_140044F5E
0x140044f41  mov     rax, [rbp+57h+var_A0]
0x140044f45  lea     rdx, [rbp+57h+var_A8]
0x140044f49  mov     r8b, [r14+r9]
0x140044f4d  lea     rcx, [rbp+57h+var_A0]
0x140044f51  mov     rax, [rax+8]
0x140044f55  call    cs:__guard_dispatch_icall_fptr
0x140044f5b  inc     r14d
0x140044f5e  mov     r9, [rbp+57h+var_78]
0x140044f62  lea     r10, cs:140000000h
0x140044f69  cmp     r14d, r15d
0x140044f6c  jb      loc_140044E83
0x140044f72  mov     r8d, [rbp+57h+var_AC]
0x140044f76  mov     rcx, cs:qword_140037EC0
0x140044f7d  lea     r10, cs:140000000h
0x140044f84  inc     r8d
0x140044f87  mov     eax, ecx
0x140044f89  mov     r9d, 3FFFFFFFh
0x140044f8f  mov     [rbp+57h+var_AC], r8d
0x140044f93  and     eax, r9d
0x140044f96  cmp     r8d, eax
0x140044f99  jb      loc_140044DE7
0x140044f9f  mov     rdx, [rbp+57h+var_A8]
0x140044fa3  lea     r10, cs:140000000h
0x140044faa  mov     r13, [rbp+57h+var_68]
0x140044fae  mov     r15, [rbp+57h+var_60]
0x140044fb2  mov     r8, 8000000000000000h
0x140044fbc  mov     rax, r15
0x140044fbf  or      rdx, r8
0x140044fc2  or      rax, r8
0x140044fc5  cmp     rdx, rax
0x140044fc8  jz      short loc_140044FD4
0x140044fca  call    sub_1400013C4
0x140044fcf  jmp     loc_14004506B
0x140044fd4  test    r12d, r12d
0x140044fd7  jz      loc_14004506B
0x140044fdd  xor     edx, edx
0x140044fdf  xor     ebx, ebx
0x140044fe1  mov     [rbp+57h+var_A8], rdx
0x140044fe5  test    r9d, ecx
0x140044fe8  jbe     short loc_14004504E
0x140044fea  mov     rsi, ds:rva qword_140037EC8[r10+rbx*8]
0x140044ff2  xor     r14d, r14d
0x140044ff5  mov     rdi, rsi
0x140044ff8  shr     rsi, 24h
0x140044ffc  add     rsi, r10
0x140044fff  shr     rdi, 6
0x140045003  and     edi, 0FFFFFFFh
0x140045009  jz      short loc_14004503A
0x14004500b  mov     rax, [rbp+57h+var_A0]
0x14004500f  lea     rdx, [rbp+57h+var_A8]
0x140045013  mov     r8b, [r14+rsi]
0x140045017  lea     rcx, [rbp+57h+var_A0]
0x14004501b  mov     rax, [rax+8]
0x14004501f  call    cs:__guard_dispatch_icall_fptr
0x140045025  inc     r14d
0x140045028  cmp     r14d, edi
0x14004502b  jb      short loc_14004500B
0x14004502d  mov     r9d, 3FFFFFFFh
0x140045033  lea     r10, cs:140000000h
0x14004503a  mov     rcx, cs:qword_140037EC0
0x140045041  inc     ebx
0x140045043  and     ecx, r9d
0x140045046  cmp     ebx, ecx
0x140045048  jb      short loc_140044FEA
0x14004504a  mov     rdx, [rbp+57h+var_A8]
0x14004504e  mov     rax, 7FFFFFFFFFFFFFFFh
0x140045058  and     rdx, rax
0x14004505b  mov     rax, r15
0x14004505e  mov     [rbp+57h+var_A8], rdx
0x140045062  lock cmpxchg cs:qword_14003A378, rdx
0x14004506b  cmp     [rbp+57h+var_B0], 0
0x14004506f  jz      short loc_14004507B
0x140045071  mov     ecx, 1
0x140045076  jmp     loc_140045114
0x14004507b  call    cs:KeEnterCriticalRegion
0x140045082  nop     dword ptr [rax+rax+00h]
0x140045087  mov     dl, 1; Wait
0x140045089  lea     rcx, stru_14003A9C0; Resource
0x140045090  call    cs:ExAcquireResourceExclusiveLite
0x140045097  nop     dword ptr [rax+rax+00h]
0x14004509c  mov     edx, 1
0x1400450a1  mov     rcx, r13
0x1400450a4  call    sub_140044C20
0x1400450a9  lea     rcx, stru_14003A9C0; Resource
0x1400450b0  call    cs:ExReleaseResourceLite
0x1400450b7  nop     dword ptr [rax+rax+00h]
0x1400450bc  call    cs:KeLeaveCriticalRegion
0x1400450c3  nop     dword ptr [rax+rax+00h]
0x1400450c8  call    cs:KeEnterCriticalRegion
0x1400450cf  nop     dword ptr [rax+rax+00h]
0x1400450d4  mov     dl, 1; Wait
0x1400450d6  lea     rcx, stru_14003A940; Resource
0x1400450dd  call    cs:ExAcquireResourceExclusiveLite
0x1400450e4  nop     dword ptr [rax+rax+00h]
0x1400450e9  xor     edx, edx
0x1400450eb  mov     rcx, r13
0x1400450ee  call    sub_140044C20
0x1400450f3  lea     rcx, stru_14003A940; Resource
0x1400450fa  call    cs:ExReleaseResourceLite
0x140045101  nop     dword ptr [rax+rax+00h]
0x140045106  call    cs:KeLeaveCriticalRegion
0x14004510d  nop     dword ptr [rax+rax+00h]
0x140045112  xor     ecx, ecx
0x140045114  mov     rdx, r13
0x140045117  call    sub_14004519C
0x14004511c  mov     rcx, [rbp+57h+Process]; Object
0x140045120  test    rcx, rcx
0x140045123  jz      short loc_140045131
0x140045125  call    cs:ObfDereferenceObject
0x14004512c  nop     dword ptr [rax+rax+00h]
0x140045131  add     rsp, 98h
0x140045138  pop     r15
0x14004513a  pop     r14
0x14004513c  pop     r13
0x14004513e  pop     r12
0x140045140  pop     rdi
0x140045141  pop     rsi
0x140045142  pop     rbx
0x140045143  pop     rbp
0x140045144  retn
```
