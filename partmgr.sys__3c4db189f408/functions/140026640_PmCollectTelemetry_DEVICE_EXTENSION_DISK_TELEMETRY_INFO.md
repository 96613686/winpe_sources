# PmCollectTelemetry(_DEVICE_EXTENSION *,_DISK_TELEMETRY_INFO * *)

- ea: `0x140026640`
- end: `0x140026f3c`
- name: `?PmCollectTelemetry@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DISK_TELEMETRY_INFO@@@Z`
- size: `2300`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DISK_TELEMETRY_INFO **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1400087c0`

## callees

- `0x140004b28`
- `0x1400050c0`
- `0x140005950`
- `0x140007bcc`
- `0x140009704`
- `0x140009880`
- `0x14000e62c`
- `0x140010e56`
- `0x140010f20`
- `0x140023cb4`
- `0x140026640`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140026eff`
- `ntoskrnl!ObfDereferenceObject` at `0x140026eff`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1400267ce`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1400267ce`
- `ntoskrnl!ExAllocatePool2` at `0x140026716`
- `ntoskrnl!ExAllocatePool2` at `0x140026cd9`
- `ntoskrnl!ExAllocatePool2` at `0x140026e0c`
- `ntoskrnl!ExAllocatePool2` at `0x140026716`
- `ntoskrnl!ExAllocatePool2` at `0x140026cd9`
- `ntoskrnl!ExAllocatePool2` at `0x140026e0c`

## pseudocode

```c
__int64 __fastcall PmCollectTelemetry(struct _DEVICE_EXTENSION *a1, struct _DISK_TELEMETRY_INFO **a2)
{
  _BYTE *DeviceExtension; // rbp
  const wchar_t *v5; // rcx
  const wchar_t *v6; // rbx
  int Sectors; // r14d
  __int64 Pool2; // rdi
  _DWORD *v9; // rcx
  struct _DEVICE_OBJECT *v10; // rbx
  char v11; // bp
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  unsigned int v13; // edx
  unsigned __int8 v14; // r8
  char v15; // cl
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rdx
  __int128 v19; // xmm0
  __int64 v20; // xmm1_8
  int v21; // r8d
  __int128 v22; // xmm0
  struct _UNICODE_STRING *v23; // rax
  __int128 v24; // xmm0
  __int128 v25; // xmm0
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 BestStorageDeviceId; // rcx
  unsigned __int64 v29; // r8
  __int64 v30; // rcx
  _DWORD *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rcx
  _DWORD *v35; // rcx
  __int64 v36; // rcx
  _DWORD *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  char v40; // cl
  __int64 v41; // rax
  __int128 *v42; // rcx
  __int64 v43; // rdx
  __int128 v44; // xmm0
  __int64 v45; // rdx
  unsigned int v46; // ebx
  unsigned int v47; // ebp
  char v48; // al
  __int64 v49; // rax
  __int64 v50; // r15
  __int64 v51; // rax
  __int128 *v52; // rcx
  __int64 v53; // rdx
  __int128 v54; // xmm0
  __int64 *i; // rdx
  unsigned int v56; // eax
  __int64 v58; // [rsp+40h] [rbp-1F8h] BYREF
  _QWORD v59[29]; // [rsp+50h] [rbp-1E8h] BYREF
  unsigned int v60; // [rsp+13Ch] [rbp-FCh]
  char v61; // [rsp+140h] [rbp-F8h]
  __int64 v62; // [rsp+148h] [rbp-F0h]
  __int128 *v63; // [rsp+158h] [rbp-E0h]
  PVOID Object[2]; // [rsp+1E0h] [rbp-58h]

  SC_DISK::SC_DISK((SC_DISK *)v59);
  v59[0] = &PM_DISK::`vftable';
  *(_OWORD *)Object = 0;
  DeviceExtension = PmControlObject->DeviceExtension;
  *a2 = 0;
  v5 = (const wchar_t *)*((_QWORD *)a1 + 44);
  v58 = 0;
  if ( v5
    && (v6 = (const wchar_t *)*((_QWORD *)a1 + 46)) != 0
    && !wcsncmp_0(v5, L"MSFT", 4u)
    && !wcsncmp_0(v6, L"XVSC", 4u) )
  {
    Sectors = -1073741637;
  }
  else
  {
    Pool2 = ExAllocatePool2(64, (unsigned int)(4 * *((_DWORD *)a1 + 229) + 504), 1112829264);
    if ( Pool2 )
    {
      if ( (*((_DWORD *)a1 + 129) & 0x20) != 0 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x10000uLL;
      }
      else if ( (*((_QWORD *)a1 + 66) & 0x40) == 0 )
      {
        if ( (int)PmGetDriveLayoutEx((KSPIN_LOCK *)a1, (struct _DRIVE_LAYOUT_INFORMATION_EX **)(Pool2 + 424)) < 0 )
        {
          *(_DWORD *)(Pool2 + 408) = *((_DWORD *)a1 + 228);
          *(_DWORD *)(Pool2 + 412) = *((_DWORD *)a1 + 229);
        }
        else
        {
          v9 = *(_DWORD **)(Pool2 + 424);
          *(_DWORD *)(Pool2 + 408) = *v9;
          *(_DWORD *)(Pool2 + 412) = v9[1];
          LODWORD(v9) = 144 * v9[1] + 48;
          *(_QWORD *)(Pool2 + 184) |= 0x8000uLL;
          *(_DWORD *)(Pool2 + 416) = (_DWORD)v9;
        }
        v10 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
        v11 = DeviceExtension[169];
        DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(v10);
        Object[1] = v10;
        Object[0] = DeviceAttachmentBaseRef;
        if ( (int)SC_DISK::Initialize((SC_DISK *)v59) >= 0
          && (v11 || (int)SC_DISK::InitializePartitionCache((SC_DISK *)v59, v13, v14) >= 0) )
        {
          v15 = v61;
          *(_DWORD *)(Pool2 + 64) = v60;
          *(_QWORD *)(Pool2 + 72) = v62 << v15;
        }
      }
      *(_DWORD *)Pool2 = *((_DWORD *)a1 + 42);
      v16 = *((_QWORD *)a1 + 1);
      *(_DWORD *)(Pool2 + 4) = *(_DWORD *)(v16 + 48);
      v17 = *(_DWORD *)(v16 + 52);
      *(_BYTE *)(Pool2 + 12) = *((_BYTE *)a1 + 604);
      *(_DWORD *)(Pool2 + 16) = *((_DWORD *)a1 + 148);
      *(_DWORD *)(Pool2 + 20) = *((_DWORD *)a1 + 149);
      *(_DWORD *)(Pool2 + 24) = *((_DWORD *)a1 + 150);
      *(_DWORD *)(Pool2 + 28) = *((_DWORD *)a1 + 130);
      v18 = *((_QWORD *)a1 + 29);
      v19 = *((_OWORD *)a1 + 34);
      *(_QWORD *)(Pool2 + 32) = *((_QWORD *)a1 + 66);
      v20 = *((_QWORD *)a1 + 53);
      *(_QWORD *)(Pool2 + 40) = *((_QWORD *)a1 + 67);
      *(_DWORD *)(Pool2 + 8) = v17;
      *(_OWORD *)(Pool2 + 48) = v19;
      v21 = *(_DWORD *)(v18 + 28);
      v22 = *(_OWORD *)((char *)a1 + 408);
      *(_DWORD *)(Pool2 + 80) = v21;
      *(_QWORD *)(Pool2 + 88) = (char *)a1 + 344;
      *(_QWORD *)(Pool2 + 96) = (char *)a1 + 360;
      *(_QWORD *)(Pool2 + 104) = (char *)a1 + 376;
      *(_QWORD *)(Pool2 + 112) = (char *)a1 + 392;
      *(_DWORD *)(Pool2 + 168) = *((_DWORD *)a1 + 108);
      *(_DWORD *)(Pool2 + 172) = *((_DWORD *)a1 + 109);
      *(_DWORD *)(Pool2 + 176) = *((_DWORD *)a1 + 110);
      v23 = &NullString;
      *(_OWORD *)(Pool2 + 144) = v22;
      *(_QWORD *)(Pool2 + 120) = (char *)a1 + 448;
      *(_QWORD *)(Pool2 + 160) = v20;
      if ( *(_DWORD *)(v18 + 28) != 15 )
        v23 = (struct _UNICODE_STRING *)((char *)a1 + 448);
      *(_QWORD *)(Pool2 + 128) = v23;
      *(_QWORD *)(Pool2 + 136) = (char *)a1 + 464;
      *(_DWORD *)(Pool2 + 192) = *((_DWORD *)a1 + 43);
      if ( *((_QWORD *)a1 + 23) != *(_QWORD *)&GUID_NULL.Data1 || *((_QWORD *)a1 + 24) != *(_QWORD *)GUID_NULL.Data4 )
      {
        v24 = *(_OWORD *)((char *)a1 + 184);
        *(_QWORD *)(Pool2 + 184) |= 1uLL;
        *(_OWORD *)(Pool2 + 196) = v24;
      }
      if ( *((_QWORD *)a1 + 25) != *(_QWORD *)&GUID_NULL.Data1 || *((_QWORD *)a1 + 26) != *(_QWORD *)GUID_NULL.Data4 )
      {
        v25 = *(_OWORD *)((char *)a1 + 200);
        *(_QWORD *)(Pool2 + 184) |= 2uLL;
        *(_OWORD *)(Pool2 + 212) = v25;
      }
      *(_OWORD *)(Pool2 + 228) = *(_OWORD *)((char *)a1 + 216);
      if ( v21 == 16 )
        *(_OWORD *)(Pool2 + 244) = *(_OWORD *)(*((_QWORD *)a1 + 29) + 36LL);
      v26 = *((_QWORD *)a1 + 30);
      if ( v26 )
      {
        *(_QWORD *)(Pool2 + 184) |= 4uLL;
        *(_BYTE *)(Pool2 + 260) = *(_BYTE *)(v26 + 8) & 1;
        *(_BYTE *)(Pool2 + 261) = *(_BYTE *)(v26 + 9);
      }
      v27 = *((_QWORD *)a1 + 31);
      if ( v27 )
      {
        *(_QWORD *)(Pool2 + 184) |= 8uLL;
        BestStorageDeviceId = StRtlFindBestStorageDeviceId(v27);
        if ( BestStorageDeviceId || *(_DWORD *)(v27 + 8) && (BestStorageDeviceId = v27 + 12, v27 != -12) )
        {
          v29 = BestStorageDeviceId + *(unsigned __int16 *)(BestStorageDeviceId + 8) + 16LL;
          if ( v29 <= v27 + (unsigned __int64)*(unsigned int *)(v27 + 4) && v29 >= BestStorageDeviceId + 16 )
          {
            *(_DWORD *)(Pool2 + 264) = *(_DWORD *)(v27 + 8);
            *(_DWORD *)(Pool2 + 268) = *(_DWORD *)BestStorageDeviceId;
            *(_DWORD *)(Pool2 + 272) = *(_DWORD *)(BestStorageDeviceId + 4);
            *(_DWORD *)(Pool2 + 276) = *(_DWORD *)(BestStorageDeviceId + 12);
            *(_QWORD *)(Pool2 + 280) = BestStorageDeviceId + 16;
            *(_DWORD *)(Pool2 + 288) = *(unsigned __int16 *)(BestStorageDeviceId + 8);
          }
        }
      }
      v30 = *((_QWORD *)a1 + 32);
      if ( v30 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x10uLL;
        *(_DWORD *)(Pool2 + 292) = *(_DWORD *)(v30 + 8);
        *(_DWORD *)(Pool2 + 296) = *(_DWORD *)(v30 + 12);
        *(_DWORD *)(Pool2 + 300) = *(_DWORD *)(v30 + 16);
        *(_DWORD *)(Pool2 + 304) = *(_DWORD *)(v30 + 20);
        *(_BYTE *)(Pool2 + 308) = *(_BYTE *)(v30 + 24);
        *(_BYTE *)(Pool2 + 309) = *(_BYTE *)(v30 + 25);
        *(_BYTE *)(Pool2 + 310) = *(_BYTE *)(v30 + 26);
      }
      v31 = (_DWORD *)*((_QWORD *)a1 + 33);
      if ( v31 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x20uLL;
        *(_DWORD *)(Pool2 + 312) = v31[4];
        *(_DWORD *)(Pool2 + 316) = v31[5];
        *(_DWORD *)(Pool2 + 320) = v31[6];
      }
      v32 = *((_QWORD *)a1 + 34);
      if ( v32 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x40uLL;
        *(_BYTE *)(Pool2 + 324) = *(_BYTE *)(v32 + 8);
      }
      v33 = *((_QWORD *)a1 + 35);
      if ( v33 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x80uLL;
        *(_BYTE *)(Pool2 + 325) = *(_BYTE *)(v33 + 8);
      }
      v34 = *((_QWORD *)a1 + 36);
      if ( v34 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x100uLL;
        *(_BYTE *)(Pool2 + 326) = *(_BYTE *)(v34 + 8) & 1;
        *(_QWORD *)(Pool2 + 328) = *(_QWORD *)(v34 + 16);
        if ( (*(_BYTE *)(v34 + 8) & 0x20) != 0 )
          *(_QWORD *)(Pool2 + 336) = *(_QWORD *)(v34 + 24);
      }
      v35 = (_DWORD *)*((_QWORD *)a1 + 37);
      if ( v35 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x200uLL;
        *(_DWORD *)(Pool2 + 344) = v35[3];
        *(_DWORD *)(Pool2 + 348) = v35[4];
        *(_DWORD *)(Pool2 + 352) = v35[5];
        *(_DWORD *)(Pool2 + 356) = v35[6];
        *(_DWORD *)(Pool2 + 360) = v35[7];
      }
      v36 = *((_QWORD *)a1 + 39);
      if ( v36 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x400uLL;
        *(_BYTE *)(Pool2 + 364) = *(_BYTE *)(v36 + 72);
        *(_QWORD *)(Pool2 + 368) = *(_QWORD *)(v36 + 96) * *(unsigned int *)(Pool2 + 64);
      }
      v37 = (_DWORD *)*((_QWORD *)a1 + 40);
      if ( v37 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x800uLL;
        *(_DWORD *)(Pool2 + 376) = v37[2];
        *(_DWORD *)(Pool2 + 380) = v37[3];
        *(_DWORD *)(Pool2 + 384) = v37[4];
      }
      v38 = *((_QWORD *)a1 + 41);
      if ( v38 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x1000uLL;
        *(_QWORD *)(Pool2 + 392) = v38 + 8;
      }
      v39 = *((_QWORD *)a1 + 42);
      if ( v39 )
      {
        *(_QWORD *)(Pool2 + 184) |= 0x2000uLL;
        *(_DWORD *)(Pool2 + 400) = *(_DWORD *)(v39 + 8);
      }
      Sectors = PmSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 2), 0x2D0C14u, 0, 0, &v58, 8u, 0);
      if ( Sectors < 0 )
      {
        Sectors = 0;
      }
      else
      {
        v40 = BYTE6(v58);
        *(_QWORD *)(Pool2 + 184) |= 0x4000uLL;
        *(_BYTE *)(Pool2 + 404) = v40;
      }
      if ( v63 )
      {
        v41 = ExAllocatePool2(66, 512, 1112829264);
        *(_QWORD *)(Pool2 + 432) = v41;
        if ( v41 )
        {
          v42 = v63;
          v43 = 4;
          do
          {
            v41 += 128;
            v44 = *v42;
            v42 += 8;
            *(_OWORD *)(v41 - 128) = v44;
            *(_OWORD *)(v41 - 112) = *(v42 - 7);
            *(_OWORD *)(v41 - 96) = *(v42 - 6);
            *(_OWORD *)(v41 - 80) = *(v42 - 5);
            *(_OWORD *)(v41 - 64) = *(v42 - 4);
            *(_OWORD *)(v41 - 48) = *(v42 - 3);
            *(_OWORD *)(v41 - 32) = *(v42 - 2);
            *(_OWORD *)(v41 - 16) = *(v42 - 1);
            --v43;
          }
          while ( v43 );
          *(_DWORD *)(Pool2 + 440) = 512;
        }
        if ( !*(_DWORD *)(Pool2 + 408) )
        {
          v45 = *(_QWORD *)(Pool2 + 424);
          if ( v45 )
          {
            if ( *(_DWORD *)(v45 + 4) )
            {
              v46 = 0;
              v47 = 0;
              do
              {
                if ( v47 >= 4 )
                  break;
                if ( *(_QWORD *)(v45 + 144LL * v46 + 64) )
                {
                  v48 = *(_BYTE *)(v45 + 144LL * v46 + 80);
                  if ( v48 == 5 || v48 == 15 )
                  {
                    v49 = *(_QWORD *)(v45 + 144LL * v46 + 56);
                    v50 = v47++;
                    if ( v60 )
                      v49 /= (__int64)v60;
                    Sectors = SC_DISK::ReadSectors((SC_DISK *)v59, 1, v49, 0);
                    if ( Sectors >= 0 )
                    {
                      v51 = ExAllocatePool2(66, 512, 1112829264);
                      *(_QWORD *)(Pool2 + 8 * v50 + 448) = v51;
                      if ( v51 )
                      {
                        v52 = v63;
                        v53 = 4;
                        do
                        {
                          v51 += 128;
                          v54 = *v52;
                          v52 += 8;
                          *(_OWORD *)(v51 - 128) = v54;
                          *(_OWORD *)(v51 - 112) = *(v52 - 7);
                          *(_OWORD *)(v51 - 96) = *(v52 - 6);
                          *(_OWORD *)(v51 - 80) = *(v52 - 5);
                          *(_OWORD *)(v51 - 64) = *(v52 - 4);
                          *(_OWORD *)(v51 - 48) = *(v52 - 3);
                          *(_OWORD *)(v51 - 32) = *(v52 - 2);
                          *(_OWORD *)(v51 - 16) = *(v52 - 1);
                          --v53;
                        }
                        while ( v53 );
                        *(_DWORD *)(Pool2 + 4 * v50 + 480) = 512;
                      }
                    }
                  }
                }
                v45 = *(_QWORD *)(Pool2 + 424);
                ++v46;
              }
              while ( v46 < *(_DWORD *)(v45 + 4) );
            }
          }
        }
      }
      for ( i = (__int64 *)*((_QWORD *)a1 + 112); i != (__int64 *)((char *)a1 + 896); i = (__int64 *)*i )
      {
        if ( (*(_DWORD *)(i - 13) & 0x40) != 0 )
        {
          v56 = *(_DWORD *)(Pool2 + 496);
          if ( v56 == *((_DWORD *)a1 + 229) )
            break;
          *(_DWORD *)(Pool2 + 4LL * v56 + 500) = *((_DWORD *)i + 12);
          ++*(_DWORD *)(Pool2 + 496);
        }
      }
      *a2 = (struct _DISK_TELEMETRY_INFO *)Pool2;
    }
    else
    {
      Sectors = -1073741670;
    }
    v59[0] = &PM_DISK::`vftable';
    if ( Object[0] )
      ObfDereferenceObject(Object[0]);
  }
  SC_DISK::~SC_DISK((SC_DISK *)v59);
  return (unsigned int)Sectors;
}

```

## disassembly

```asm
0x140026640  push    rbx
0x140026642  push    rbp
0x140026643  push    rsi
0x140026644  push    r12
0x140026646  push    r13
0x140026648  push    r14
0x14002664a  push    r15
0x14002664c  sub     rsp, 200h
0x140026653  mov     rax, cs:__security_cookie
0x14002665a  xor     rax, rsp
0x14002665d  mov     [rsp+238h+var_48], rax
0x140026665  mov     rsi, rcx
0x140026668  mov     r12, rdx
0x14002666b  lea     rcx, [rsp+238h+var_1E8]; this
0x140026670  call    ??0SC_DISK@@QEAA@XZ; SC_DISK::SC_DISK(void)
0x140026675  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14002667c  lea     r13, ??_7PM_DISK@@6B@; const PM_DISK::`vftable'
0x140026683  xor     r15d, r15d
0x140026686  mov     [rsp+238h+var_1E8], r13
0x14002668b  xorps   xmm2, xmm2
0x14002668e  movdqa  xmmword ptr [rsp+238h+Object], xmm2
0x140026697  mov     rbp, [rax+40h]
0x14002669b  mov     [r12], r15
0x14002669f  mov     rcx, [rsi+160h]; Str1
0x1400266a6  mov     [rsp+238h+var_1F8], r15
0x1400266ab  test    rcx, rcx
0x1400266ae  jz      short loc_1400266F6
0x1400266b0  mov     rbx, [rsi+170h]
0x1400266b7  test    rbx, rbx
0x1400266ba  jz      short loc_1400266F6
0x1400266bc  mov     r8d, 4; MaxCount
0x1400266c2  lea     rdx, aMsft_0; "MSFT"
0x1400266c9  call    wcsncmp_0
0x1400266ce  test    eax, eax
0x1400266d0  jnz     short loc_1400266F6
0x1400266d2  mov     r8d, 4; MaxCount
0x1400266d8  lea     rdx, aXvsc; "XVSC"
0x1400266df  mov     rcx, rbx; Str1
0x1400266e2  call    wcsncmp_0
0x1400266e7  test    eax, eax
0x1400266e9  jnz     short loc_1400266F6
0x1400266eb  mov     r14d, 0C00000BBh
0x1400266f1  jmp     loc_140026F0B
0x1400266f6  mov     eax, [rsi+394h]
0x1400266fc  mov     ecx, 40h ; '@'
0x140026701  mov     r8d, 42546D50h
0x140026707  mov     [rsp+238h+arg_10], rdi
0x14002670f  lea     edx, ds:1F8h[rax*4]
0x140026716  call    cs:__imp_ExAllocatePool2
0x14002671d  nop     dword ptr [rax+rax+00h]
0x140026722  mov     rdi, rax
0x140026725  test    rax, rax
0x140026728  jnz     short loc_140026735
0x14002672a  mov     r14d, 0C000009Ah
0x140026730  jmp     loc_140026EE5
0x140026735  mov     eax, [rsi+204h]
0x14002673b  test    al, 20h
0x14002673d  jz      short loc_14002674F
0x14002673f  or      qword ptr [rdi+0B8h], 10000h
0x14002674a  jmp     loc_14002682B
0x14002674f  mov     rax, [rsi+210h]
0x140026756  test    al, 40h
0x140026758  jnz     loc_14002682B
0x14002675e  lea     rdx, [rdi+1A8h]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140026765  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140026768  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002676d  test    eax, eax
0x14002676f  js      short loc_1400267A8
0x140026771  mov     rcx, [rdi+1A8h]
0x140026778  mov     eax, [rcx]
0x14002677a  mov     [rdi+198h], eax
0x140026780  mov     eax, [rcx+4]
0x140026783  mov     [rdi+19Ch], eax
0x140026789  mov     eax, [rcx+4]
0x14002678c  lea     ecx, [rax+rax*8]
0x14002678f  shl     ecx, 4
0x140026792  add     ecx, 30h ; '0'
0x140026795  or      qword ptr [rdi+0B8h], 8000h
0x1400267a0  mov     [rdi+1A0h], ecx
0x1400267a6  jmp     short loc_1400267C0
0x1400267a8  mov     eax, [rsi+390h]
0x1400267ae  mov     [rdi+198h], eax
0x1400267b4  mov     eax, [rsi+394h]
0x1400267ba  mov     [rdi+19Ch], eax
0x1400267c0  mov     rbx, [rsi+8]
0x1400267c4  movzx   ebp, byte ptr [rbp+0A9h]
0x1400267cb  mov     rcx, rbx; DeviceObject
0x1400267ce  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x1400267d5  nop     dword ptr [rax+rax+00h]
0x1400267da  lea     rcx, [rsp+238h+var_1E8]; this
0x1400267df  mov     [rsp+238h+Object+8], rbx
0x1400267e7  mov     [rsp+238h+Object], rax
0x1400267ef  call    ?Initialize@SC_DISK@@UEAAJXZ; SC_DISK::Initialize(void)
0x1400267f4  test    eax, eax
0x1400267f6  js      short loc_14002682B
0x1400267f8  test    bpl, bpl
0x1400267fb  jnz     short loc_14002680B
0x1400267fd  lea     rcx, [rsp+238h+var_1E8]; this
0x140026802  call    ?InitializePartitionCache@SC_DISK@@QEAAJXZ; SC_DISK::InitializePartitionCache(void)
0x140026807  test    eax, eax
0x140026809  js      short loc_14002682B
0x14002680b  mov     eax, dword ptr [rsp+238h+var_FC]
0x140026812  mov     ecx, dword ptr [rsp+238h+var_FC+4]
0x140026819  mov     [rdi+40h], eax
0x14002681c  mov     rax, [rsp+238h+var_F0]
0x140026824  shl     rax, cl
0x140026827  mov     [rdi+48h], rax
0x14002682b  mov     eax, [rsi+0A8h]
0x140026831  mov     [rdi], eax
0x140026833  mov     rax, [rsi+8]
0x140026837  mov     ecx, [rax+30h]
0x14002683a  mov     rax, [rsi+8]
0x14002683e  mov     [rdi+4], ecx
0x140026841  mov     ecx, [rax+34h]
0x140026844  movzx   eax, byte ptr [rsi+25Ch]
0x14002684b  mov     [rdi+0Ch], al
0x14002684e  mov     eax, [rsi+250h]
0x140026854  mov     [rdi+10h], eax
0x140026857  mov     eax, [rsi+254h]
0x14002685d  mov     [rdi+14h], eax
0x140026860  mov     eax, [rsi+258h]
0x140026866  mov     [rdi+18h], eax
0x140026869  mov     eax, [rsi+208h]
0x14002686f  mov     [rdi+1Ch], eax
0x140026872  mov     rax, [rsi+210h]
0x140026879  mov     rdx, [rsi+0E8h]
0x140026880  movups  xmm0, xmmword ptr [rsi+220h]
0x140026887  mov     [rdi+20h], rax
0x14002688b  mov     rax, [rsi+218h]
0x140026892  movsd   xmm1, qword ptr [rsi+1A8h]
0x14002689a  mov     [rdi+28h], rax
0x14002689e  lea     rax, [rsi+158h]
0x1400268a5  mov     [rdi+8], ecx
0x1400268a8  lea     rcx, [rsi+1C0h]
0x1400268af  movups  xmmword ptr [rdi+30h], xmm0
0x1400268b3  mov     r8d, [rdx+1Ch]
0x1400268b7  movups  xmm0, xmmword ptr [rsi+198h]
0x1400268be  mov     [rdi+50h], r8d
0x1400268c2  mov     [rdi+58h], rax
0x1400268c6  lea     rax, [rsi+168h]
0x1400268cd  mov     [rdi+60h], rax
0x1400268d1  lea     rax, [rsi+178h]
0x1400268d8  mov     [rdi+68h], rax
0x1400268dc  lea     rax, [rsi+188h]
0x1400268e3  mov     [rdi+70h], rax
0x1400268e7  mov     eax, [rsi+1B0h]
0x1400268ed  mov     [rdi+0A8h], eax
0x1400268f3  mov     eax, [rsi+1B4h]
0x1400268f9  mov     [rdi+0ACh], eax
0x1400268ff  mov     eax, [rsi+1B8h]
0x140026905  mov     [rdi+0B0h], eax
0x14002690b  lea     rax, ?NullString@@3U_UNICODE_STRING@@A; _UNICODE_STRING NullString
0x140026912  movups  xmmword ptr [rdi+90h], xmm0
0x140026919  mov     [rdi+78h], rcx
0x14002691d  movsd   qword ptr [rdi+0A0h], xmm1
0x140026925  cmp     dword ptr [rdx+1Ch], 0Fh
0x140026929  cmovnz  rax, rcx
0x14002692d  mov     [rdi+80h], rax
0x140026934  lea     rax, [rsi+1D0h]
0x14002693b  mov     rdx, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x140026942  mov     rcx, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x140026949  mov     [rdi+88h], rax
0x140026950  mov     eax, [rsi+0ACh]
0x140026956  mov     [rdi+0C0h], eax
0x14002695c  cmp     [rsi+0B8h], rdx
0x140026963  jnz     short loc_14002696E
0x140026965  cmp     [rsi+0C0h], rcx
0x14002696c  jz      short loc_140026984
0x14002696e  movups  xmm0, xmmword ptr [rsi+0B8h]
0x140026975  or      qword ptr [rdi+0B8h], 1
0x14002697d  movups  xmmword ptr [rdi+0C4h], xmm0
0x140026984  cmp     [rsi+0C8h], rdx
0x14002698b  jnz     short loc_140026996
0x14002698d  cmp     [rsi+0D0h], rcx
0x140026994  jz      short loc_1400269AC
0x140026996  movups  xmm0, xmmword ptr [rsi+0C8h]
0x14002699d  or      qword ptr [rdi+0B8h], 2
0x1400269a5  movups  xmmword ptr [rdi+0D4h], xmm0
0x1400269ac  movups  xmm0, xmmword ptr [rsi+0D8h]
0x1400269b3  movups  xmmword ptr [rdi+0E4h], xmm0
0x1400269ba  cmp     r8d, 10h
0x1400269be  jnz     short loc_1400269D2
0x1400269c0  mov     rax, [rsi+0E8h]
0x1400269c7  movups  xmm0, xmmword ptr [rax+24h]
0x1400269cb  movups  xmmword ptr [rdi+0F4h], xmm0
0x1400269d2  mov     rcx, [rsi+0F0h]
0x1400269d9  test    rcx, rcx
0x1400269dc  jz      short loc_1400269FC
0x1400269de  or      qword ptr [rdi+0B8h], 4
0x1400269e6  movzx   eax, byte ptr [rcx+8]
0x1400269ea  and     al, 1
0x1400269ec  mov     [rdi+104h], al
0x1400269f2  movzx   eax, byte ptr [rcx+9]
0x1400269f6  mov     [rdi+105h], al
0x1400269fc  mov     rbx, [rsi+0F8h]
0x140026a03  test    rbx, rbx
0x140026a06  jz      short loc_140026A83
0x140026a08  or      qword ptr [rdi+0B8h], 8
0x140026a10  mov     rcx, rbx
0x140026a13  call    StRtlFindBestStorageDeviceId
0x140026a18  mov     rcx, rax
0x140026a1b  test    rax, rax
0x140026a1e  jnz     short loc_140026A2F
0x140026a20  cmp     [rbx+8], r15d
0x140026a24  jbe     short loc_140026A83
0x140026a26  lea     rcx, [rbx+0Ch]
0x140026a2a  test    rcx, rcx
0x140026a2d  jz      short loc_140026A83
0x140026a2f  movzx   r8d, word ptr [rcx+8]
0x140026a34  mov     eax, [rbx+4]
0x140026a37  add     r8, 10h
0x140026a3b  add     r8, rcx
0x140026a3e  add     rax, rbx
0x140026a41  cmp     r8, rax
0x140026a44  ja      short loc_140026A83
0x140026a46  lea     r9, [rcx+10h]
0x140026a4a  cmp     r8, r9
0x140026a4d  jb      short loc_140026A83
0x140026a4f  mov     eax, [rbx+8]
0x140026a52  mov     [rdi+108h], eax
0x140026a58  mov     eax, [rcx]
0x140026a5a  mov     [rdi+10Ch], eax
0x140026a60  mov     eax, [rcx+4]
0x140026a63  mov     [rdi+110h], eax
0x140026a69  mov     eax, [rcx+0Ch]
0x140026a6c  mov     [rdi+114h], eax
0x140026a72  mov     [rdi+118h], r9
0x140026a79  movzx   eax, word ptr [rcx+8]
0x140026a7d  mov     [rdi+120h], eax
0x140026a83  mov     rcx, [rsi+100h]
0x140026a8a  test    rcx, rcx
0x140026a8d  jz      short loc_140026AD9
0x140026a8f  or      qword ptr [rdi+0B8h], 10h
0x140026a97  mov     eax, [rcx+8]
0x140026a9a  mov     [rdi+124h], eax
0x140026aa0  mov     eax, [rcx+0Ch]
0x140026aa3  mov     [rdi+128h], eax
0x140026aa9  mov     eax, [rcx+10h]
0x140026aac  mov     [rdi+12Ch], eax
0x140026ab2  mov     eax, [rcx+14h]
0x140026ab5  mov     [rdi+130h], eax
0x140026abb  movzx   eax, byte ptr [rcx+18h]
0x140026abf  mov     [rdi+134h], al
0x140026ac5  movzx   eax, byte ptr [rcx+19h]
0x140026ac9  mov     [rdi+135h], al
0x140026acf  movzx   eax, byte ptr [rcx+1Ah]
0x140026ad3  mov     [rdi+136h], al
0x140026ad9  mov     rcx, [rsi+108h]
0x140026ae0  test    rcx, rcx
0x140026ae3  jz      short loc_140026B08
0x140026ae5  or      qword ptr [rdi+0B8h], 20h
0x140026aed  mov     eax, [rcx+10h]
0x140026af0  mov     [rdi+138h], eax
0x140026af6  mov     eax, [rcx+14h]
0x140026af9  mov     [rdi+13Ch], eax
0x140026aff  mov     eax, [rcx+18h]
0x140026b02  mov     [rdi+140h], eax
0x140026b08  mov     rax, [rsi+110h]
0x140026b0f  test    rax, rax
0x140026b12  jz      short loc_140026B26
0x140026b14  or      qword ptr [rdi+0B8h], 40h
0x140026b1c  movzx   eax, byte ptr [rax+8]
0x140026b20  mov     [rdi+144h], al
0x140026b26  mov     rax, [rsi+118h]
0x140026b2d  test    rax, rax
0x140026b30  jz      short loc_140026B47
0x140026b32  or      qword ptr [rdi+0B8h], 80h
0x140026b3d  movzx   eax, byte ptr [rax+8]
0x140026b41  mov     [rdi+145h], al
0x140026b47  mov     rcx, [rsi+120h]
0x140026b4e  test    rcx, rcx
0x140026b51  jz      short loc_140026B86
0x140026b53  or      qword ptr [rdi+0B8h], 100h
0x140026b5e  movzx   eax, byte ptr [rcx+8]
0x140026b62  and     al, 1
0x140026b64  mov     [rdi+146h], al
0x140026b6a  mov     rax, [rcx+10h]
0x140026b6e  mov     [rdi+148h], rax
0x140026b75  test    byte ptr [rcx+8], 20h
0x140026b79  jz      short loc_140026B86
0x140026b7b  mov     rax, [rcx+18h]
0x140026b7f  mov     [rdi+150h], rax
0x140026b86  mov     rcx, [rsi+128h]
0x140026b8d  test    rcx, rcx
0x140026b90  jz      short loc_140026BCA
0x140026b92  or      qword ptr [rdi+0B8h], 200h
0x140026b9d  mov     eax, [rcx+0Ch]
0x140026ba0  mov     [rdi+158h], eax
0x140026ba6  mov     eax, [rcx+10h]
0x140026ba9  mov     [rdi+15Ch], eax
0x140026baf  mov     eax, [rcx+14h]
0x140026bb2  mov     [rdi+160h], eax
0x140026bb8  mov     eax, [rcx+18h]
0x140026bbb  mov     [rdi+164h], eax
0x140026bc1  mov     eax, [rcx+1Ch]
0x140026bc4  mov     [rdi+168h], eax
0x140026bca  mov     rcx, [rsi+138h]
0x140026bd1  test    rcx, rcx
0x140026bd4  jz      short loc_140026BFA
0x140026bd6  or      qword ptr [rdi+0B8h], 400h
  ... truncated ...
```
