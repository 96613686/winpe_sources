# VfIovPluginEntry

- ea: `0x14063bac0`
- end: `0x14063bcf9`
- name: `VfIovPluginEntry`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14053fcf0`
- `0x1406dc8c0`
- `0x140bc2fcc`

## string_xrefs

- `0x14063bb4c`: `IoReleaseRemoveLockAndWaitEx`
- `0x14063bb04`: `IoInitializeRemoveLockEx`
- `0x14063bb1c`: `IoAcquireRemoveLockEx`
- `0x14063bb34`: `IoReleaseRemoveLockEx`

## pseudocode

```c
__int64 VfIovPluginEntry()
{
  const char *v1; // [rsp+20h] [rbp-E0h] BYREF
  int v2; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall *v3)(); // [rsp+30h] [rbp-D0h]
  __int64 v4; // [rsp+38h] [rbp-C8h]
  const char *v5; // [rsp+40h] [rbp-C0h]
  int v6; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall *v7)(); // [rsp+50h] [rbp-B0h]
  __int64 v8; // [rsp+58h] [rbp-A8h]
  const char *v9; // [rsp+60h] [rbp-A0h]
  int v10; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v11)(); // [rsp+70h] [rbp-90h]
  __int64 v12; // [rsp+78h] [rbp-88h]
  const char *v13; // [rsp+80h] [rbp-80h]
  int v14; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v15)(); // [rsp+90h] [rbp-70h]
  __int64 v16; // [rsp+98h] [rbp-68h]
  const char *v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v19)(); // [rsp+B0h] [rbp-50h]
  __int64 v20; // [rsp+B8h] [rbp-48h]
  const char *v21; // [rsp+C0h] [rbp-40h]
  int v22; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v23)(); // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+D8h] [rbp-28h]
  const char *v25; // [rsp+E0h] [rbp-20h]
  int v26; // [rsp+E8h] [rbp-18h]
  __int64 v27; // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v28)(); // [rsp+F8h] [rbp-8h]
  const char *v29; // [rsp+100h] [rbp+0h]
  int v30; // [rsp+108h] [rbp+8h]
  __int64 v31; // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v32)(); // [rsp+118h] [rbp+18h]
  const char *v33; // [rsp+120h] [rbp+20h]
  int v34; // [rsp+128h] [rbp+28h]
  __int64 v35; // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v36)(); // [rsp+138h] [rbp+38h]
  const char *v37; // [rsp+140h] [rbp+40h]
  int v38; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v39)(); // [rsp+150h] [rbp+50h]
  __int64 v40; // [rsp+158h] [rbp+58h]
  const char *v41; // [rsp+160h] [rbp+60h]
  int v42; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v43)(); // [rsp+170h] [rbp+70h]
  __int64 v44; // [rsp+178h] [rbp+78h]
  const char *v45; // [rsp+180h] [rbp+80h]
  int v46; // [rsp+188h] [rbp+88h]
  __int64 (__fastcall *v47)(); // [rsp+190h] [rbp+90h]
  __int64 v48; // [rsp+198h] [rbp+98h]
  const char *v49; // [rsp+1A0h] [rbp+A0h]
  int v50; // [rsp+1A8h] [rbp+A8h]
  __int64 (__fastcall *v51)(); // [rsp+1B0h] [rbp+B0h]
  __int64 v52; // [rsp+1B8h] [rbp+B8h]

  ViIovInitialization();
  v2 = 330;
  v4 = 0;
  qword_140EF2468 = (__int64)ViIovPluginUnload;
  v1 = "IoInitializeRemoveLockEx";
  v3 = ViSpIoAllocateIrp_Exit;
  v5 = "IoAcquireRemoveLockEx";
  v7 = ViSpIoAllocateIrp_Exit;
  v9 = "IoReleaseRemoveLockEx";
  v11 = ViSpIoAllocateIrp_Exit;
  v13 = "IoReleaseRemoveLockAndWaitEx";
  v15 = ViSpIoAllocateIrp_Exit;
  v17 = "ExFreePool";
  v19 = ViIovExFreePool_Entry;
  v21 = "ExFreePoolWithTag";
  v23 = ViIovExFreePoolWithTag_Entry;
  v25 = "IoBuildAsynchronousFsdRequest";
  v28 = ViIovIoBuildAsynchronousFsdRequest_Exit;
  v29 = "IoBuildDeviceIoControlRequest";
  v32 = ViIovIoBuildDeviceIoControlRequest_Exit;
  v33 = "IoBuildSynchronousFsdRequest";
  v36 = ViIovIoBuildSynchronousFsdRequest_Exit;
  v37 = "IoAllocateIrp";
  v39 = ViSpIoAllocateIrp_Exit;
  v41 = "IoAllocateIrpEx";
  v43 = ViSpIoAllocateIrp_Exit;
  v45 = "IoInitializeTimer";
  v47 = ViIoInitializeTimer_Entry;
  v49 = "IoFreeIrp";
  v51 = ViSpIoAllocateIrp_Exit;
  v6 = 371;
  v8 = 0;
  v10 = 316;
  v12 = 0;
  v14 = 317;
  v16 = 0;
  v18 = 401;
  v20 = 0;
  v22 = 400;
  v24 = 0;
  v26 = 362;
  v27 = 0;
  v30 = 361;
  v31 = 0;
  v34 = 360;
  v35 = 0;
  v38 = 366;
  v40 = 0;
  v42 = 367;
  v44 = 0;
  v46 = 329;
  v48 = 0;
  v50 = 340;
  v52 = 0;
  return DifRegisterPlugin((__int64)&v1, 0xDu, 4u, (__int64)&ViIovPluginSetting);
}

```

## disassembly

```asm
0x14063bac0  push    rbp
0x14063bac2  lea     rbp, [rsp-0D0h]
0x14063baca  sub     rsp, 1D0h
0x14063bad1  mov     rax, cs:__security_cookie
0x14063bad8  xor     rax, rsp
0x14063badb  mov     [rbp+0D0h+var_10], rax
0x14063bae2  call    ViIovInitialization
0x14063bae7  xor     ecx, ecx
0x14063bae9  mov     [rsp+1D0h+var_1A8], 14Ah
0x14063baf1  lea     rax, ViIovPluginUnload
0x14063baf8  mov     [rsp+1D0h+var_198], rcx
0x14063bafd  mov     cs:qword_140EF2468, rax
0x14063bb04  lea     rax, aIoinitializere; "IoInitializeRemoveLockEx"
0x14063bb0b  mov     [rsp+1D0h+var_1B0], rax
0x14063bb10  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bb17  mov     [rsp+1D0h+var_1A0], rax
0x14063bb1c  lea     rax, aIoacquireremov; "IoAcquireRemoveLockEx"
0x14063bb23  mov     [rsp+1D0h+var_190], rax
0x14063bb28  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bb2f  mov     [rsp+1D0h+var_180], rax
0x14063bb34  lea     rax, aIoreleaseremov; "IoReleaseRemoveLockEx"
0x14063bb3b  mov     [rsp+1D0h+var_170], rax
0x14063bb40  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bb47  mov     [rsp+1D0h+var_160], rax
0x14063bb4c  lea     rax, aIoreleaseremov_1; "IoReleaseRemoveLockAndWaitEx"
0x14063bb53  mov     [rbp+0D0h+var_150], rax
0x14063bb57  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bb5e  mov     [rbp+0D0h+var_140], rax
0x14063bb62  lea     rax, aExfreepool_1; "ExFreePool"
0x14063bb69  mov     [rbp+0D0h+var_130], rax
0x14063bb6d  lea     rax, ViIovExFreePool_Entry
0x14063bb74  mov     [rbp+0D0h+var_120], rax
0x14063bb78  lea     rax, aExfreepoolwith_1; "ExFreePoolWithTag"
0x14063bb7f  mov     [rbp+0D0h+var_110], rax
0x14063bb83  lea     rax, ViIovExFreePoolWithTag_Entry
0x14063bb8a  mov     [rbp+0D0h+var_100], rax
0x14063bb8e  lea     rax, aIobuildasynchr; "IoBuildAsynchronousFsdRequest"
0x14063bb95  mov     [rbp+0D0h+var_F0], rax
0x14063bb99  lea     rax, ViIovIoBuildAsynchronousFsdRequest_Exit
0x14063bba0  mov     [rbp+0D0h+var_D8], rax
0x14063bba4  lea     rax, aIobuilddevicei_0; "IoBuildDeviceIoControlRequest"
0x14063bbab  mov     [rbp+0D0h+var_D0], rax
0x14063bbaf  lea     rax, ViIovIoBuildDeviceIoControlRequest_Exit
0x14063bbb6  mov     [rbp+0D0h+var_B8], rax
0x14063bbba  lea     rax, aIobuildsynchro; "IoBuildSynchronousFsdRequest"
0x14063bbc1  mov     [rbp+0D0h+var_B0], rax
0x14063bbc5  lea     rax, ViIovIoBuildSynchronousFsdRequest_Exit
0x14063bbcc  mov     [rbp+0D0h+var_98], rax
0x14063bbd0  lea     rax, aIoallocateirp_1; "IoAllocateIrp"
0x14063bbd7  mov     [rbp+0D0h+var_90], rax
0x14063bbdb  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bbe2  mov     [rbp+0D0h+var_80], rax
0x14063bbe6  lea     rax, aIoallocateirpe_0; "IoAllocateIrpEx"
0x14063bbed  mov     [rbp+0D0h+var_70], rax
0x14063bbf1  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bbf8  mov     [rbp+0D0h+var_60], rax
0x14063bbfc  lea     rax, aIoinitializeti; "IoInitializeTimer"
0x14063bc03  mov     [rbp+0D0h+var_50], rax
0x14063bc0a  lea     rax, ViIoInitializeTimer_Entry
0x14063bc11  mov     [rbp+0D0h+var_40], rax
0x14063bc18  lea     rax, aIofreeirp; "IoFreeIrp"
0x14063bc1f  mov     [rbp+0D0h+var_30], rax
0x14063bc26  lea     rax, ViSpIoAllocateIrp_Exit
0x14063bc2d  mov     [rbp+0D0h+var_20], rax
0x14063bc34  mov     [rsp+1D0h+var_188], 173h
0x14063bc3c  mov     [rsp+1D0h+var_178], rcx
0x14063bc41  mov     [rsp+1D0h+var_168], 13Ch
0x14063bc49  mov     [rsp+1D0h+var_158], rcx
0x14063bc4e  mov     [rbp+0D0h+var_148], 13Dh
0x14063bc55  mov     [rbp+0D0h+var_138], rcx
0x14063bc59  mov     [rbp+0D0h+var_128], 191h
0x14063bc60  mov     [rbp+0D0h+var_118], rcx
0x14063bc64  mov     [rbp+0D0h+var_108], 190h
0x14063bc6b  mov     [rbp+0D0h+var_F8], rcx
0x14063bc6f  mov     [rbp+0D0h+var_E8], 16Ah
0x14063bc76  mov     [rbp+0D0h+var_E0], rcx
0x14063bc7a  mov     [rbp+0D0h+var_C8], 169h
0x14063bc81  mov     [rbp+0D0h+var_C0], rcx
0x14063bc85  mov     [rbp+0D0h+var_A8], 168h
0x14063bc8c  mov     [rbp+0D0h+var_A0], rcx
0x14063bc90  mov     [rbp+0D0h+var_88], 16Eh
0x14063bc97  mov     [rbp+0D0h+var_78], rcx
0x14063bc9b  mov     [rbp+0D0h+var_68], 16Fh
0x14063bca2  mov     [rbp+0D0h+var_58], rcx
0x14063bca6  mov     [rbp+0D0h+var_48], 149h
0x14063bcb0  mov     [rbp+0D0h+var_38], rcx
0x14063bcb7  mov     [rbp+0D0h+var_28], 154h
0x14063bcc1  mov     [rbp+0D0h+var_18], rcx
0x14063bcc8  lea     edx, [rcx+0Dh]
0x14063bccb  lea     r8d, [rcx+4]
0x14063bccf  lea     rcx, [rsp+1D0h+var_1B0]
0x14063bcd4  lea     r9, ViIovPluginSetting
0x14063bcdb  call    DifRegisterPlugin
0x14063bce0  mov     rcx, [rbp+0D0h+var_10]
0x14063bce7  xor     rcx, rsp; StackCookie
0x14063bcea  call    __security_check_cookie
0x14063bcef  add     rsp, 1D0h
0x14063bcf6  pop     rbp
0x14063bcf7  retn
```
