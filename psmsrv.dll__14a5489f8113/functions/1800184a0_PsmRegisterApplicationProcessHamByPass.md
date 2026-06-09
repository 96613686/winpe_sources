# PsmRegisterApplicationProcessHamByPass

- ea: `0x1800184a0`
- end: `0x1800187b0`
- name: `PsmRegisterApplicationProcessHamByPass`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800180d0`

## callees

- `0x180009b40`
- `0x18000cb7c`
- `0x18000f580`
- `0x1800114d0`
- `0x180013610`
- `0x1800137a4`
- `0x1800184a0`
- `0x1800188f8`
- `0x1800192fc`
- `0x18001b7e0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x1800185c3`
- `ntdll!NtSetEvent` at `0x1800185c3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800186a7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800186a7`

## pseudocode

```c
__int64 __fastcall PsmRegisterApplicationProcessHamByPass(
        void *a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  int v9; // eax
  __int64 v10; // rbx
  int v11; // esi
  int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // r15d
  int v16; // r12d
  int v17; // r13d
  __int64 v18; // rbx
  DWORD ProcessId; // eax
  int v20; // eax
  char v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Process; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v26; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+80h] [rbp-80h] BYREF
  int *v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  char v35[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  DWORD *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  unsigned int *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  int *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  __int64 *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  __int64 *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  HANDLE *p_Process; // [rsp+120h] [rbp+20h]
  __int64 v49; // [rsp+128h] [rbp+28h]
  __int64 *v50; // [rsp+130h] [rbp+30h]
  __int64 v51; // [rsp+138h] [rbp+38h]
  __int64 v52; // [rsp+140h] [rbp+40h]
  int v53; // [rsp+148h] [rbp+48h]
  int v54; // [rsp+14Ch] [rbp+4Ch]

  v29 = a4;
  v30 = a3;
  Process = a1;
  v23 = 0;
  v9 = PsmpAllocateOrLookupApplicationEx(a3, a5, a6, &v23);
  v10 = v23;
  v11 = v9;
  v12 = 11;
  if ( v9 >= 0 )
  {
    if ( (a5 & 0xD) == 0 && (unsigned int)(*(_DWORD *)(v23 + 344) - 5) <= 1 )
      PsmpChangeApplicationState(
        v23,
        0,
        (__int64 (__fastcall *)(__int64, __int64, unsigned int *, __int64 *))PsmpPrepareToAddProcess,
        0xBu,
        1,
        0);
    v22[0] = 0;
    v11 = PsmpAddProcessToApplication(v10, a3, a5, Process, a2, a4, v22);
    if ( v11 >= 0 )
    {
      if ( (a5 & 1) != 0 )
        PsmpChangeApplicationState(
          v10,
          0,
          (__int64 (__fastcall *)(__int64, __int64, unsigned int *, __int64 *))PsmpExitBackgroundState,
          0xBu,
          1,
          0);
      if ( v22[0] )
        NtSetEvent(*(HANDLE *)(*(_QWORD *)(v10 + 320) + 56LL), 0);
      LOBYTE(v23) = Microsoft_Windows_ProcessStateManagerEnableBits & 0x20;
      if ( (Microsoft_Windows_ProcessStateManagerEnableBits & 0x20) != 0 )
        McTemplateU0xqzqx_EventWriteTransfer(
          v14,
          v13,
          *(_QWORD *)(v10 + 96),
          *(_DWORD *)(*(_QWORD *)(v10 + 312) + 4LL),
          *(const wchar_t **)(v10 + 8),
          a5,
          a4);
    }
  }
  if ( v10 )
  {
    v12 = *(_DWORD *)(v10 + 344);
    v15 = *(_DWORD *)(v10 + 136);
    v16 = *(_DWORD *)(v10 + 140);
    v17 = *(_DWORD *)(v10 + 144);
  }
  else
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
  }
  if ( v10 )
    PsmpDereferenceApplicationEx(v10, 0);
  if ( (unsigned int)dword_18003F080 > 4 && tlgKeywordOn((__int64)&dword_18003F080, 3) )
  {
    v18 = v30;
    v25 = v11;
    v33 = &v25;
    v34 = 4;
    tlgCreate1Sz_wchar_t((__int64)v35, (char *)(v30 + 8));
    v36 = &v31;
    v31 = v29;
    v37 = 8;
    ProcessId = GetProcessId(Process);
    v39 = 4;
    v26 = ProcessId;
    v54 = 0;
    v38 = &v26;
    v27 = a5;
    v40 = &v27;
    v41 = 4;
    v42 = &v28;
    v28 = v12;
    v44 = &v29;
    v46 = &v30;
    p_Process = &Process;
    LODWORD(v23) = *(_DWORD *)v18;
    v50 = &v23;
    v52 = v18 + 472;
    v20 = *(unsigned __int8 *)(v18 + 473);
    v43 = 4;
    LODWORD(v29) = v15;
    v45 = 4;
    LODWORD(v30) = v16;
    v53 = 4 * v20 + 8;
    v47 = 4;
    LODWORD(Process) = v17;
    v49 = 4;
    v51 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18003F080, (unsigned __int8 *)byte_180037F6F, 0, 0, 0xDu, &v32);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800184a0  push    rbp
0x1800184a2  push    rbx
0x1800184a3  push    rsi
0x1800184a4  push    rdi
0x1800184a5  push    r12
0x1800184a7  push    r13
0x1800184a9  push    r14
0x1800184ab  push    r15
0x1800184ad  lea     rbp, [rsp-68h]
0x1800184b2  sub     rsp, 168h
0x1800184b9  mov     rax, cs:__security_cookie
0x1800184c0  xor     rax, rsp
0x1800184c3  mov     [rbp+0A0h+var_50], rax
0x1800184c7  mov     edi, [rbp+0A0h+arg_20]
0x1800184cd  mov     r12, r8
0x1800184d0  mov     r15, r9
0x1800184d3  mov     [rsp+1A0h+var_138], r9
0x1800184d8  mov     [rsp+1A0h+var_130], r8
0x1800184dd  lea     r9, [rsp+1A0h+var_158]
0x1800184e2  mov     r8, [rbp+0A0h+arg_28]
0x1800184e9  mov     r13, rdx
0x1800184ec  mov     [rsp+1A0h+Process], rcx
0x1800184f1  mov     edx, edi
0x1800184f3  mov     rcx, r12
0x1800184f6  mov     [rsp+1A0h+var_158], 0
0x1800184ff  call    PsmpAllocateOrLookupApplicationEx
0x180018504  mov     rbx, [rsp+1A0h+var_158]
0x180018509  mov     esi, eax
0x18001850b  mov     r14d, 0Bh
0x180018511  test    eax, eax
0x180018513  js      loc_1800185FD
0x180018519  test    dil, 0Dh
0x18001851d  jnz     short loc_180018552
0x18001851f  mov     eax, [rbx+158h]
0x180018525  sub     eax, 5
0x180018528  cmp     eax, 1
0x18001852b  ja      short loc_180018552
0x18001852d  mov     [rsp+1A0h+var_178], 0
0x180018536  lea     r8, PsmpPrepareToAddProcess
0x18001853d  mov     r9d, r14d
0x180018540  mov     dword ptr [rsp+1A0h+var_180], 1
0x180018548  xor     edx, edx
0x18001854a  mov     rcx, rbx
0x18001854d  call    PsmpChangeApplicationState
0x180018552  mov     r9, [rsp+1A0h+Process]
0x180018557  lea     rax, [rsp+1A0h+var_160]
0x18001855c  mov     [rsp+1A0h+var_170], rax
0x180018561  mov     r8d, edi
0x180018564  mov     [rsp+1A0h+var_178], r15
0x180018569  mov     rdx, r12
0x18001856c  mov     rcx, rbx
0x18001856f  mov     [rsp+1A0h+var_180], r13
0x180018574  mov     [rsp+1A0h+var_160], 0
0x180018579  call    PsmpAddProcessToApplication
0x18001857e  mov     esi, eax
0x180018580  test    eax, eax
0x180018582  js      short loc_1800185FD
0x180018584  test    dil, 1
0x180018588  jz      short loc_1800185AF
0x18001858a  mov     [rsp+1A0h+var_178], 0
0x180018593  lea     r8, PsmpExitBackgroundState
0x18001859a  mov     r9d, r14d
0x18001859d  mov     dword ptr [rsp+1A0h+var_180], 1
0x1800185a5  xor     edx, edx
0x1800185a7  mov     rcx, rbx
0x1800185aa  call    PsmpChangeApplicationState
0x1800185af  cmp     [rsp+1A0h+var_160], 0
0x1800185b4  jz      short loc_1800185C9
0x1800185b6  mov     rcx, [rbx+140h]
0x1800185bd  xor     edx, edx; PreviousState
0x1800185bf  mov     rcx, [rcx+38h]; EventHandle
0x1800185c3  call    cs:__imp_NtSetEvent
0x1800185c9  mov     al, cs:Microsoft_Windows_ProcessStateManagerEnableBits
0x1800185cf  and     al, 20h
0x1800185d1  mov     byte ptr [rsp+1A0h+var_158], al
0x1800185d5  jz      short loc_1800185FD
0x1800185d7  mov     r9, [rbx+138h]
0x1800185de  mov     rax, [rbx+8]
0x1800185e2  mov     r8, [rbx+60h]
0x1800185e6  mov     [rsp+1A0h+var_170], r15
0x1800185eb  mov     r9d, [r9+4]
0x1800185ef  mov     dword ptr [rsp+1A0h+var_178], edi
0x1800185f3  mov     [rsp+1A0h+var_180], rax
0x1800185f8  call    McTemplateU0xqzqx_EventWriteTransfer
0x1800185fd  test    rbx, rbx
0x180018600  jz      short loc_180018620
0x180018602  mov     r14d, [rbx+158h]
0x180018609  mov     r15d, [rbx+88h]
0x180018610  mov     r12d, [rbx+8Ch]
0x180018617  mov     r13d, [rbx+90h]
0x18001861e  jmp     short loc_180018629
0x180018620  xor     r15d, r15d
0x180018623  xor     r12d, r12d
0x180018626  xor     r13d, r13d
0x180018629  test    rbx, rbx
0x18001862c  jz      short loc_180018638
0x18001862e  xor     edx, edx
0x180018630  mov     rcx, rbx
0x180018633  call    PsmpDereferenceApplicationEx
0x180018638  mov     eax, cs:dword_18003F080
0x18001863e  cmp     eax, 4
0x180018641  jbe     loc_18001878E
0x180018647  mov     edx, 3
0x18001864c  lea     rcx, dword_18003F080
0x180018653  call    _tlgKeywordOn
0x180018658  test    al, al
0x18001865a  jz      loc_18001878E
0x180018660  mov     rbx, [rsp+1A0h+var_130]
0x180018665  lea     rax, [rsp+1A0h+var_148]
0x18001866a  lea     rcx, [rbp+0A0h+var_F0]
0x18001866e  mov     [rsp+1A0h+var_148], esi
0x180018672  mov     [rbp+0A0h+var_100], rax
0x180018676  mov     [rbp+0A0h+var_F8], 4
0x18001867e  lea     rdx, [rbx+8]
0x180018682  call    _tlgCreate1Sz_wchar_t
0x180018687  mov     r8, [rsp+1A0h+var_138]
0x18001868c  lea     rax, [rsp+1A0h+var_128]
0x180018691  mov     rcx, [rsp+1A0h+Process]; Process
0x180018696  mov     [rbp+0A0h+var_E0], rax
0x18001869a  mov     [rsp+1A0h+var_128], r8
0x18001869f  mov     [rbp+0A0h+var_D8], 8
0x1800186a7  call    cs:__imp_GetProcessId
0x1800186ad  xor     ecx, ecx
0x1800186af  mov     [rbp+0A0h+var_C8], 4
0x1800186b7  mov     [rsp+1A0h+var_144], eax
0x1800186bb  lea     rdx, byte_180037F6F
0x1800186c2  lea     rax, [rsp+1A0h+var_144]
0x1800186c7  mov     [rbp+0A0h+var_54], ecx
0x1800186ca  mov     [rbp+0A0h+var_D0], rax
0x1800186ce  lea     rcx, dword_18003F080
0x1800186d5  lea     rax, [rsp+1A0h+var_140]
0x1800186da  mov     [rsp+1A0h+var_140], edi
0x1800186de  mov     [rbp+0A0h+var_C0], rax
0x1800186e2  xor     r9d, r9d
0x1800186e5  lea     rax, [rsp+1A0h+var_13C]
0x1800186ea  mov     [rbp+0A0h+var_B8], 4
0x1800186f2  mov     [rbp+0A0h+var_B0], rax
0x1800186f6  xor     r8d, r8d
0x1800186f9  lea     rax, [rsp+1A0h+var_138]
0x1800186fe  mov     [rsp+1A0h+var_13C], r14d
0x180018703  mov     [rbp+0A0h+var_A0], rax
0x180018707  lea     rax, [rsp+1A0h+var_130]
0x18001870c  mov     [rbp+0A0h+var_90], rax
0x180018710  lea     rax, [rsp+1A0h+Process]
0x180018715  mov     [rbp+0A0h+var_80], rax
0x180018719  mov     eax, [rbx]
0x18001871b  mov     dword ptr [rsp+1A0h+var_158], eax
0x18001871f  lea     rax, [rsp+1A0h+var_158]
0x180018724  mov     [rbp+0A0h+var_70], rax
0x180018728  lea     rax, [rbx+1D8h]
0x18001872f  mov     [rbp+0A0h+var_60], rax
0x180018733  movzx   eax, byte ptr [rax+1]
0x180018737  mov     [rbp+0A0h+var_A8], 4
0x18001873f  mov     dword ptr [rsp+1A0h+var_138], r15d
0x180018744  mov     [rbp+0A0h+var_98], 4
0x18001874c  lea     eax, ds:8[rax*4]
0x180018753  mov     dword ptr [rsp+1A0h+var_130], r12d
0x180018758  mov     [rbp+0A0h+var_58], eax
0x18001875b  lea     rax, [rbp+0A0h+var_120]
0x18001875f  mov     [rsp+1A0h+var_178], rax
0x180018764  mov     dword ptr [rsp+1A0h+var_180], 0Dh
0x18001876c  mov     [rbp+0A0h+var_88], 4
0x180018774  mov     dword ptr [rsp+1A0h+Process], r13d
0x180018779  mov     [rbp+0A0h+var_78], 4
0x180018781  mov     [rbp+0A0h+var_68], 4
0x180018789  call    _tlgWriteTransfer_EventWriteTransfer
0x18001878e  mov     eax, esi
0x180018790  mov     rcx, [rbp+0A0h+var_50]
0x180018794  xor     rcx, rsp; StackCookie
0x180018797  call    __security_check_cookie
0x18001879c  add     rsp, 168h
0x1800187a3  pop     r15
0x1800187a5  pop     r14
0x1800187a7  pop     r13
0x1800187a9  pop     r12
0x1800187ab  pop     rdi
0x1800187ac  pop     rsi
0x1800187ad  pop     rbx
0x1800187ae  pop     rbp
0x1800187af  retn
```
