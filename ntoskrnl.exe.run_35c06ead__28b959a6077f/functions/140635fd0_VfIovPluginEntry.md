# VfIovPluginEntry

- ea: `0x140635fd0`
- end: `0x140636209`
- name: `VfIovPluginEntry`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140538640`
- `0x1406d9d70`
- `0x140bbffcc`

## string_xrefs

- `0x14063605c`: `IoReleaseRemoveLockAndWaitEx`
- `0x140636044`: `IoReleaseRemoveLockEx`
- `0x14063602c`: `IoAcquireRemoveLockEx`
- `0x140636014`: `IoInitializeRemoveLockEx`

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
  qword_140EF25A8 = (__int64)ViIovPluginUnload;
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
  return ((__int64 (__fastcall *)(const char **, __int64, __int64, __int64 *))DifRegisterPlugin)(
           &v1,
           13,
           4,
           &ViIovPluginSetting);
}

```

## disassembly

```asm
0x140635fd0  push    rbp
0x140635fd2  lea     rbp, [rsp-0D0h]
0x140635fda  sub     rsp, 1D0h
0x140635fe1  mov     rax, cs:__security_cookie
0x140635fe8  xor     rax, rsp
0x140635feb  mov     [rbp+0D0h+var_10], rax
0x140635ff2  call    ViIovInitialization
0x140635ff7  xor     ecx, ecx
0x140635ff9  mov     [rsp+1D0h+var_1A8], 14Ah
0x140636001  lea     rax, ViIovPluginUnload
0x140636008  mov     [rsp+1D0h+var_198], rcx
0x14063600d  mov     cs:qword_140EF25A8, rax
0x140636014  lea     rax, aIoinitializere; "IoInitializeRemoveLockEx"
0x14063601b  mov     [rsp+1D0h+var_1B0], rax
0x140636020  lea     rax, ViSpIoAllocateIrp_Exit
0x140636027  mov     [rsp+1D0h+var_1A0], rax
0x14063602c  lea     rax, aIoacquireremov; "IoAcquireRemoveLockEx"
0x140636033  mov     [rsp+1D0h+var_190], rax
0x140636038  lea     rax, ViSpIoAllocateIrp_Exit
0x14063603f  mov     [rsp+1D0h+var_180], rax
0x140636044  lea     rax, aIoreleaseremov; "IoReleaseRemoveLockEx"
0x14063604b  mov     [rsp+1D0h+var_170], rax
0x140636050  lea     rax, ViSpIoAllocateIrp_Exit
0x140636057  mov     [rsp+1D0h+var_160], rax
0x14063605c  lea     rax, aIoreleaseremov_1; "IoReleaseRemoveLockAndWaitEx"
0x140636063  mov     [rbp+0D0h+var_150], rax
0x140636067  lea     rax, ViSpIoAllocateIrp_Exit
0x14063606e  mov     [rbp+0D0h+var_140], rax
0x140636072  lea     rax, aExfreepool_1; "ExFreePool"
0x140636079  mov     [rbp+0D0h+var_130], rax
0x14063607d  lea     rax, ViIovExFreePool_Entry
0x140636084  mov     [rbp+0D0h+var_120], rax
0x140636088  lea     rax, aExfreepoolwith_1; "ExFreePoolWithTag"
0x14063608f  mov     [rbp+0D0h+var_110], rax
0x140636093  lea     rax, ViIovExFreePoolWithTag_Entry
0x14063609a  mov     [rbp+0D0h+var_100], rax
0x14063609e  lea     rax, aIobuildasynchr; "IoBuildAsynchronousFsdRequest"
0x1406360a5  mov     [rbp+0D0h+var_F0], rax
0x1406360a9  lea     rax, ViIovIoBuildAsynchronousFsdRequest_Exit
0x1406360b0  mov     [rbp+0D0h+var_D8], rax
0x1406360b4  lea     rax, aIobuilddevicei_0; "IoBuildDeviceIoControlRequest"
0x1406360bb  mov     [rbp+0D0h+var_D0], rax
0x1406360bf  lea     rax, ViIovIoBuildDeviceIoControlRequest_Exit
0x1406360c6  mov     [rbp+0D0h+var_B8], rax
0x1406360ca  lea     rax, aIobuildsynchro; "IoBuildSynchronousFsdRequest"
0x1406360d1  mov     [rbp+0D0h+var_B0], rax
0x1406360d5  lea     rax, ViIovIoBuildSynchronousFsdRequest_Exit
0x1406360dc  mov     [rbp+0D0h+var_98], rax
0x1406360e0  lea     rax, aIoallocateirp_1; "IoAllocateIrp"
0x1406360e7  mov     [rbp+0D0h+var_90], rax
0x1406360eb  lea     rax, ViSpIoAllocateIrp_Exit
0x1406360f2  mov     [rbp+0D0h+var_80], rax
0x1406360f6  lea     rax, aIoallocateirpe_0; "IoAllocateIrpEx"
0x1406360fd  mov     [rbp+0D0h+var_70], rax
0x140636101  lea     rax, ViSpIoAllocateIrp_Exit
0x140636108  mov     [rbp+0D0h+var_60], rax
0x14063610c  lea     rax, aIoinitializeti; "IoInitializeTimer"
0x140636113  mov     [rbp+0D0h+var_50], rax
0x14063611a  lea     rax, ViIoInitializeTimer_Entry
0x140636121  mov     [rbp+0D0h+var_40], rax
0x140636128  lea     rax, aIofreeirp; "IoFreeIrp"
0x14063612f  mov     [rbp+0D0h+var_30], rax
0x140636136  lea     rax, ViSpIoAllocateIrp_Exit
0x14063613d  mov     [rbp+0D0h+var_20], rax
0x140636144  mov     [rsp+1D0h+var_188], 173h
0x14063614c  mov     [rsp+1D0h+var_178], rcx
0x140636151  mov     [rsp+1D0h+var_168], 13Ch
0x140636159  mov     [rsp+1D0h+var_158], rcx
0x14063615e  mov     [rbp+0D0h+var_148], 13Dh
0x140636165  mov     [rbp+0D0h+var_138], rcx
0x140636169  mov     [rbp+0D0h+var_128], 191h
0x140636170  mov     [rbp+0D0h+var_118], rcx
0x140636174  mov     [rbp+0D0h+var_108], 190h
0x14063617b  mov     [rbp+0D0h+var_F8], rcx
0x14063617f  mov     [rbp+0D0h+var_E8], 16Ah
0x140636186  mov     [rbp+0D0h+var_E0], rcx
0x14063618a  mov     [rbp+0D0h+var_C8], 169h
0x140636191  mov     [rbp+0D0h+var_C0], rcx
0x140636195  mov     [rbp+0D0h+var_A8], 168h
0x14063619c  mov     [rbp+0D0h+var_A0], rcx
0x1406361a0  mov     [rbp+0D0h+var_88], 16Eh
0x1406361a7  mov     [rbp+0D0h+var_78], rcx
0x1406361ab  mov     [rbp+0D0h+var_68], 16Fh
0x1406361b2  mov     [rbp+0D0h+var_58], rcx
0x1406361b6  mov     [rbp+0D0h+var_48], 149h
0x1406361c0  mov     [rbp+0D0h+var_38], rcx
0x1406361c7  mov     [rbp+0D0h+var_28], 154h
0x1406361d1  mov     [rbp+0D0h+var_18], rcx
0x1406361d8  lea     edx, [rcx+0Dh]
0x1406361db  lea     r8d, [rcx+4]
0x1406361df  lea     rcx, [rsp+1D0h+var_1B0]
0x1406361e4  lea     r9, ViIovPluginSetting
0x1406361eb  call    DifRegisterPlugin
0x1406361f0  mov     rcx, [rbp+0D0h+var_10]
0x1406361f7  xor     rcx, rsp; StackCookie
0x1406361fa  call    __security_check_cookie
0x1406361ff  add     rsp, 1D0h
0x140636206  pop     rbp
0x140636207  retn
```
