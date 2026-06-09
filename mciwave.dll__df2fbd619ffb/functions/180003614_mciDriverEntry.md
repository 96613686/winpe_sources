# mciDriverEntry

- ea: `0x180003614`
- end: `0x180003a3b`
- name: `mciDriverEntry`
- size: `1063`
- prototype: `__int64 __fastcall(MCIDEVICEID wDeviceID)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180005430`

## callees

- `0x180002914`
- `0x1800029f4`
- `0x1800034a8`
- `0x180003568`
- `0x180003614`
- `0x180003c68`
- `0x180003d64`
- `0x1800040dc`
- `0x180004508`
- `0x1800046f0`
- `0x18000492c`
- `0x180004d18`
- `0x1800050b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003890`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000387a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000387a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003871`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003871`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003887`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003887`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003865`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003865`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a25`
- `USER32!PostThreadMessageW` at `0x180003851`
- `USER32!PostThreadMessageW` at `0x180003851`
- `WINMM!waveOutRestart` at `0x1800039b8`
- `WINMM!waveOutRestart` at `0x1800039b8`
- `WINMM!mciGetDriverData` at `0x18000362b`
- `WINMM!mciGetDriverData` at `0x18000362b`
- `WINMM!mciDriverNotify` at `0x180003a03`
- `WINMM!mciDriverNotify` at `0x180003a18`
- `WINMM!mciDriverNotify` at `0x180003a03`
- `WINMM!mciDriverNotify` at `0x180003a18`
- `WINMM!waveOutPause` at `0x180003762`
- `WINMM!waveOutPause` at `0x180003762`
- `WINMM!waveInStart` at `0x1800039c4`
- `WINMM!waveInStart` at `0x1800039c4`
- `WINMM!waveInStop` at `0x180003772`
- `WINMM!waveInStop` at `0x180003772`

## pseudocode

```c
__int64 __fastcall mciDriverEntry(MCIDEVICEID wDeviceID, unsigned int a2, unsigned int a3, __int64 a4)
{
  DWORD_PTR DriverData; // rdi
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  __int64 v15; // rbx
  int v17; // eax
  MMRESULT v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // ebx
  __int64 v21; // r9
  DWORD v22; // ecx
  void *v23; // rbx
  unsigned int DevCaps; // eax
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  int v29; // eax
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  MMRESULT v34; // eax
  void *v35; // rcx

  DriverData = mciGetDriverData(wDeviceID);
  if ( !DriverData )
  {
    if ( a2 <= 0x813 )
    {
      if ( a2 != 2067 && a2 != 2054 && a2 != 2055 && a2 != 2056 && a2 != 2057 && a2 != 2061 && a2 != 2063 )
        goto LABEL_10;
      return 274;
    }
    if ( a2 == 2068 || a2 == 2096 || a2 == 2130 || a2 == 2131 || a2 - 2133 <= 1 )
      return 274;
  }
LABEL_10:
  EnterCriticalSection(&CritSec);
  if ( a2 > 0x830 )
  {
    v30 = a2 - 2128;
    if ( !v30 || (v31 = v30 - 2) == 0 || (v32 = v31 - 1) == 0 )
    {
      v15 = 274;
      goto LABEL_93;
    }
    v33 = v32 - 2;
    if ( !v33 )
    {
      if ( (a3 & 0xFFFFFFFC) != 0 )
        goto LABEL_21;
      if ( *(_DWORD *)(DriverData + 32) == 3 )
      {
        LODWORD(v15) = 0;
        if ( (*(_DWORD *)(DriverData + 4) & 0x2008) == 8 )
        {
          v34 = (*(_DWORD *)(DriverData + 4) & 0x200) != 0
              ? waveOutRestart(*(HWAVEOUT *)(DriverData + 48))
              : waveInStart(*(HWAVEIN *)(DriverData + 56));
          LODWORD(v15) = v34;
          if ( !v34 )
            *(_DWORD *)(DriverData + 4) &= ~8u;
        }
        goto LABEL_39;
      }
      goto LABEL_38;
    }
    if ( v33 != 1 )
    {
LABEL_82:
      v15 = 261;
      goto LABEL_93;
    }
    DevCaps = mwDelete((_DWORD *)DriverData, a3, a4);
    goto LABEL_62;
  }
  if ( a2 == 2096 )
  {
    v29 = mwCue(DriverData, a3, a4);
    goto LABEL_73;
  }
  if ( a2 <= 0x80A )
  {
    if ( a2 == 2058 )
    {
      DevCaps = mwInfo(DriverData, a3, a4);
    }
    else
    {
      v10 = a2 - 2049;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( !v11 )
        {
          if ( DriverData )
          {
            if ( *(_DWORD *)(DriverData + 24) )
            {
              mwStop(DriverData);
              v22 = *(_DWORD *)(DriverData + 24);
              *(_DWORD *)(DriverData + 32) = 4;
              PostThreadMessageW(v22, 0x401u, 0, 0);
              v23 = *(void **)(DriverData + 176);
              LeaveCriticalSection(&CritSec);
              WaitForSingleObject(v23, 0xFFFFFFFF);
              CloseHandle(v23);
              EnterCriticalSection(&CritSec);
            }
            LocalFree((HLOCAL)DriverData);
          }
          v15 = 0;
          DriverData = 0;
          goto LABEL_93;
        }
        v12 = v11 - 4;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 == 1 )
              {
                if ( (a3 & 0xFFFFFFFC) != 0 )
                {
LABEL_21:
                  LODWORD(v15) = 259;
LABEL_39:
                  v15 = (unsigned int)v15;
LABEL_93:
                  if ( !(_WORD)v15 && (a3 & 1) != 0 )
                  {
                    if ( DriverData )
                    {
                      v35 = *(void **)(DriverData + 16);
                      if ( v35 )
                      {
                        mciDriverNotify(v35, *(_DWORD *)DriverData, 2u);
                        *(_QWORD *)(DriverData + 16) = 0;
                      }
                    }
                    mciDriverNotify(*(HANDLE *)a4, wDeviceID, 1u);
                  }
                  goto LABEL_99;
                }
                if ( *(_DWORD *)(DriverData + 32) == 3 )
                {
                  v17 = *(_DWORD *)(DriverData + 4);
                  if ( (v17 & 0x2020) == 0 )
                  {
                    LODWORD(v15) = 0;
                    if ( (v17 & 8) != 0 )
                      goto LABEL_39;
                    if ( (v17 & 0x200) != 0 )
                    {
                      if ( (v17 & 0x40) == 0 )
                      {
                        v18 = waveOutPause(*(HWAVEOUT *)(DriverData + 48));
                        goto LABEL_36;
                      }
                    }
                    else if ( (v17 & 0x40) == 0 )
                    {
                      v18 = waveInStop(*(HWAVEIN *)(DriverData + 56));
LABEL_36:
                      LODWORD(v15) = v18;
                      if ( !v18 )
                        *(_DWORD *)(DriverData + 4) |= 8u;
                      goto LABEL_39;
                    }
                  }
                }
LABEL_38:
                LODWORD(v15) = 302;
                goto LABEL_39;
              }
              goto LABEL_82;
            }
            mwStop(DriverData);
          }
          else
          {
            v19 = a3 & 0xFFFFFFFC;
            if ( (a3 & 0xFFFFFFFC) == 0 )
            {
              v15 = 273;
              goto LABEL_93;
            }
            if ( (a3 & 0xFFFFFFFC) != (a3 & 0x308) )
            {
              v15 = 259;
              goto LABEL_93;
            }
            switch ( v19 )
            {
              case 8u:
                v20 = VerifyRangeEnd(DriverData, *(unsigned int *)(a4 + 8), 1);
                if ( v20 == -1 )
                {
                  v15 = 282;
                  goto LABEL_93;
                }
                break;
              case 0x100u:
                v20 = 0;
                break;
              case 0x200u:
                v20 = *(_DWORD *)(DriverData + 76);
                break;
              default:
                v15 = 284;
                goto LABEL_93;
            }
            mwStop(DriverData);
            SetCurrentPosition(DriverData, v20);
          }
          v15 = 0;
          goto LABEL_93;
        }
        v21 = 1;
        goto LABEL_72;
      }
      DevCaps = mwOpenDevice(a3, a4, wDeviceID);
    }
LABEL_62:
    v15 = DevCaps;
    goto LABEL_93;
  }
  v25 = a2 - 2059;
  if ( !v25 )
  {
    DevCaps = mwGetDevCaps(v9, a3, a4);
    goto LABEL_62;
  }
  v26 = v25 - 2;
  if ( !v26 )
  {
    DevCaps = mwSet(DriverData, a3, a4);
    goto LABEL_62;
  }
  v27 = v26 - 2;
  if ( v27 )
  {
    v28 = v27 - 4;
    if ( v28 )
    {
      if ( v28 != 1 )
        goto LABEL_82;
      DevCaps = mwStatus(DriverData, a3, a4);
    }
    else
    {
      DevCaps = mwSave(DriverData, a3, a4);
    }
    goto LABEL_62;
  }
  v21 = 0;
LABEL_72:
  v29 = mwSetup(DriverData, a3, a4, v21);
LABEL_73:
  v15 = v29;
LABEL_99:
  LeaveCriticalSection(&CritSec);
  return v15;
}

```

## disassembly

```asm
0x180003614  push    rbx
0x180003616  push    rbp
0x180003617  push    rsi
0x180003618  push    rdi
0x180003619  push    r14
0x18000361b  push    r15
0x18000361d  sub     rsp, 28h
0x180003621  mov     r14, r9
0x180003624  mov     esi, r8d
0x180003627  mov     ebx, edx
0x180003629  mov     ebp, ecx
0x18000362b  call    cs:__imp_mciGetDriverData
0x180003631  xor     r15d, r15d
0x180003634  mov     rdi, rax
0x180003637  test    rax, rax
0x18000363a  jnz     short loc_180003689
0x18000363c  mov     eax, 813h
0x180003641  cmp     ebx, eax
0x180003643  ja      loc_180003708
0x180003649  jz      loc_18000372E
0x18000364f  mov     eax, ebx
0x180003651  sub     eax, 806h
0x180003656  jz      loc_18000372E
0x18000365c  sub     eax, 1
0x18000365f  jz      loc_18000372E
0x180003665  sub     eax, 1
0x180003668  jz      loc_18000372E
0x18000366e  sub     eax, 1
0x180003671  jz      loc_18000372E
0x180003677  sub     eax, 4
0x18000367a  jz      loc_18000372E
0x180003680  cmp     eax, 2
0x180003683  jz      loc_18000372E
0x180003689  lea     rcx, CritSec; lpCriticalSection
0x180003690  call    cs:__imp_EnterCriticalSection
0x180003696  mov     eax, 830h
0x18000369b  mov     edx, 1
0x1800036a0  cmp     ebx, eax
0x1800036a2  ja      loc_180003946
0x1800036a8  jz      loc_180003937
0x1800036ae  mov     eax, 80Ah
0x1800036b3  cmp     ebx, eax
0x1800036b5  ja      loc_1800038C4
0x1800036bb  jz      loc_1800038B5
0x1800036c1  sub     ebx, 801h
0x1800036c7  jz      loc_1800038A1
0x1800036cd  sub     ebx, edx
0x1800036cf  jz      loc_180003829
0x1800036d5  sub     ebx, 4
0x1800036d8  jz      loc_180003821
0x1800036de  sub     ebx, edx
0x1800036e0  jz      loc_1800037A0
0x1800036e6  sub     ebx, edx
0x1800036e8  jz      loc_180003790
0x1800036ee  cmp     ebx, edx
0x1800036f0  jnz     loc_180003968
0x1800036f6  test    esi, 0FFFFFFFCh
0x1800036fc  jz      short loc_180003738
0x1800036fe  mov     ebx, 103h
0x180003703  jmp     loc_180003789
0x180003708  mov     eax, ebx
0x18000370a  sub     eax, 814h
0x18000370f  jz      short loc_18000372E
0x180003711  sub     eax, 1Ch
0x180003714  jz      short loc_18000372E
0x180003716  sub     eax, 22h ; '"'
0x180003719  jz      short loc_18000372E
0x18000371b  sub     eax, 1
0x18000371e  jz      short loc_18000372E
0x180003720  sub     eax, 2
0x180003723  jz      short loc_18000372E
0x180003725  cmp     eax, 1
0x180003728  jnz     loc_180003689
0x18000372e  mov     eax, 112h
0x180003733  jmp     loc_180003A2E
0x180003738  cmp     dword ptr [rdi+20h], 3
0x18000373c  jnz     short loc_180003784
0x18000373e  mov     eax, [rdi+4]
0x180003741  test    eax, 2020h
0x180003746  jnz     short loc_180003784
0x180003748  mov     ebx, r15d
0x18000374b  test    al, 8
0x18000374d  jnz     short loc_180003789
0x18000374f  mov     ecx, eax
0x180003751  and     ecx, 40h
0x180003754  bt      eax, 9
0x180003758  jnb     short loc_18000376A
0x18000375a  test    ecx, ecx
0x18000375c  jnz     short loc_180003784
0x18000375e  mov     rcx, [rdi+30h]; hwo
0x180003762  call    cs:__imp_waveOutPause
0x180003768  jmp     short loc_180003778
0x18000376a  test    ecx, ecx
0x18000376c  jnz     short loc_180003784
0x18000376e  mov     rcx, [rdi+38h]; hwi
0x180003772  call    cs:__imp_waveInStop
0x180003778  mov     ebx, eax
0x18000377a  test    eax, eax
0x18000377c  jnz     short loc_180003789
0x18000377e  or      dword ptr [rdi+4], 8
0x180003782  jmp     short loc_180003789
0x180003784  mov     ebx, 12Eh
0x180003789  mov     ebx, ebx
0x18000378b  jmp     loc_1800039E2
0x180003790  mov     rcx, rdi
0x180003793  call    mwStop
0x180003798  mov     rbx, r15
0x18000379b  jmp     loc_1800039E2
0x1800037a0  mov     ecx, esi
0x1800037a2  and     ecx, 0FFFFFFFCh
0x1800037a5  jnz     short loc_1800037B1
0x1800037a7  mov     ebx, 111h
0x1800037ac  jmp     loc_1800039E2
0x1800037b1  mov     eax, ecx
0x1800037b3  and     eax, 308h
0x1800037b8  cmp     ecx, eax
0x1800037ba  jz      short loc_1800037C6
0x1800037bc  mov     ebx, 103h
0x1800037c1  jmp     loc_1800039E2
0x1800037c6  cmp     ecx, 8
0x1800037c9  jz      short loc_180003801
0x1800037cb  cmp     ecx, 100h
0x1800037d1  jz      short loc_1800037FC
0x1800037d3  cmp     ecx, 200h
0x1800037d9  jz      short loc_1800037E5
0x1800037db  mov     ebx, 11Ch
0x1800037e0  jmp     loc_1800039E2
0x1800037e5  mov     ebx, [rdi+4Ch]
0x1800037e8  mov     rcx, rdi
0x1800037eb  call    mwStop
0x1800037f0  mov     edx, ebx
0x1800037f2  mov     rcx, rdi
0x1800037f5  call    SetCurrentPosition
0x1800037fa  jmp     short loc_180003798
0x1800037fc  mov     ebx, r15d
0x1800037ff  jmp     short loc_1800037E8
0x180003801  mov     r8d, edx
0x180003804  mov     rcx, rdi
0x180003807  mov     edx, [r14+8]
0x18000380b  call    VerifyRangeEnd
0x180003810  mov     ebx, eax
0x180003812  cmp     eax, 0FFFFFFFFh
0x180003815  jnz     short loc_1800037E8
0x180003817  mov     ebx, 11Ah
0x18000381c  jmp     loc_1800039E2
0x180003821  mov     r9d, edx
0x180003824  jmp     loc_180003904
0x180003829  test    rdi, rdi
0x18000382c  jz      short loc_180003896
0x18000382e  cmp     [rdi+18h], r15d
0x180003832  jz      short loc_18000388D
0x180003834  mov     rcx, rdi
0x180003837  call    mwStop
0x18000383c  mov     ecx, [rdi+18h]; idThread
0x18000383f  xor     r9d, r9d; lParam
0x180003842  xor     r8d, r8d; wParam
0x180003845  mov     dword ptr [rdi+20h], 4
0x18000384c  mov     edx, 401h; Msg
0x180003851  call    cs:__imp_PostThreadMessageW
0x180003857  mov     rbx, [rdi+0B0h]
0x18000385e  lea     rcx, CritSec; lpCriticalSection
0x180003865  call    cs:__imp_LeaveCriticalSection
0x18000386b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000386e  mov     rcx, rbx; hHandle
0x180003871  call    cs:__imp_WaitForSingleObject
0x180003877  mov     rcx, rbx; hObject
0x18000387a  call    cs:__imp_CloseHandle
0x180003880  lea     rcx, CritSec; lpCriticalSection
0x180003887  call    cs:__imp_EnterCriticalSection
0x18000388d  mov     rcx, rdi; hMem
0x180003890  call    cs:__imp_LocalFree
0x180003896  mov     rbx, r15
0x180003899  mov     rdi, r15
0x18000389c  jmp     loc_1800039E2
0x1800038a1  mov     r8d, ebp
0x1800038a4  mov     rdx, r14
0x1800038a7  mov     ecx, esi
0x1800038a9  call    mwOpenDevice
0x1800038ae  mov     ebx, eax
0x1800038b0  jmp     loc_1800039E2
0x1800038b5  mov     r8, r14
0x1800038b8  mov     edx, esi
0x1800038ba  mov     rcx, rdi
0x1800038bd  call    mwInfo
0x1800038c2  jmp     short loc_1800038AE
0x1800038c4  sub     ebx, 80Bh
0x1800038ca  jz      short loc_180003928
0x1800038cc  sub     ebx, 2
0x1800038cf  jz      short loc_180003919
0x1800038d1  sub     ebx, 2
0x1800038d4  jz      short loc_180003901
0x1800038d6  sub     ebx, 4
0x1800038d9  jz      short loc_1800038F2
0x1800038db  cmp     ebx, edx
0x1800038dd  jnz     loc_180003968
0x1800038e3  mov     r8, r14
0x1800038e6  mov     edx, esi
0x1800038e8  mov     rcx, rdi
0x1800038eb  call    mwStatus
0x1800038f0  jmp     short loc_1800038AE
0x1800038f2  mov     r8, r14
0x1800038f5  mov     edx, esi
0x1800038f7  mov     rcx, rdi
0x1800038fa  call    mwSave
0x1800038ff  jmp     short loc_1800038AE
0x180003901  xor     r9d, r9d
0x180003904  mov     r8, r14
0x180003907  mov     edx, esi
0x180003909  mov     rcx, rdi
0x18000390c  call    mwSetup
0x180003911  movsxd  rbx, eax
0x180003914  jmp     loc_180003A1E
0x180003919  mov     r8, r14
0x18000391c  mov     edx, esi
0x18000391e  mov     rcx, rdi
0x180003921  call    mwSet
0x180003926  jmp     short loc_1800038AE
0x180003928  mov     r8, r14
0x18000392b  mov     edx, esi
0x18000392d  call    mwGetDevCaps
0x180003932  jmp     loc_1800038AE
0x180003937  mov     r8, r14
0x18000393a  mov     edx, esi
0x18000393c  mov     rcx, rdi
0x18000393f  call    mwCue
0x180003944  jmp     short loc_180003911
0x180003946  sub     ebx, 850h
0x18000394c  jz      loc_1800039DD
0x180003952  sub     ebx, 2
0x180003955  jz      loc_1800039DD
0x18000395b  sub     ebx, edx
0x18000395d  jz      short loc_1800039DD
0x18000395f  sub     ebx, 2
0x180003962  jz      short loc_180003981
0x180003964  cmp     ebx, edx
0x180003966  jz      short loc_18000396F
0x180003968  mov     ebx, 105h
0x18000396d  jmp     short loc_1800039E2
0x18000396f  mov     r8, r14
0x180003972  mov     edx, esi
0x180003974  mov     rcx, rdi
0x180003977  call    mwDelete
0x18000397c  jmp     loc_1800038AE
0x180003981  test    esi, 0FFFFFFFCh
0x180003987  jnz     loc_1800036FE
0x18000398d  cmp     dword ptr [rdi+20h], 3
0x180003991  jnz     loc_180003784
0x180003997  mov     eax, [rdi+4]
0x18000399a  mov     ebx, r15d
0x18000399d  and     eax, 2008h
0x1800039a2  cmp     eax, 8
0x1800039a5  jnz     loc_180003789
0x1800039ab  test    dword ptr [rdi+4], 200h
0x1800039b2  jz      short loc_1800039C0
0x1800039b4  mov     rcx, [rdi+30h]; hwo
0x1800039b8  call    cs:__imp_waveOutRestart
0x1800039be  jmp     short loc_1800039CA
0x1800039c0  mov     rcx, [rdi+38h]; hwi
0x1800039c4  call    cs:__imp_waveInStart
0x1800039ca  mov     ebx, eax
0x1800039cc  test    eax, eax
0x1800039ce  jnz     loc_180003789
0x1800039d4  and     dword ptr [rdi+4], 0FFFFFFF7h
0x1800039d8  jmp     loc_180003789
0x1800039dd  mov     ebx, 112h
0x1800039e2  test    bx, bx
0x1800039e5  jnz     short loc_180003A1E
0x1800039e7  test    sil, 1
0x1800039eb  jz      short loc_180003A1E
0x1800039ed  test    rdi, rdi
0x1800039f0  jz      short loc_180003A0D
0x1800039f2  mov     rcx, [rdi+10h]; hwndCallback
0x1800039f6  test    rcx, rcx
0x1800039f9  jz      short loc_180003A0D
0x1800039fb  mov     edx, [rdi]; wDeviceID
0x1800039fd  mov     r8d, 2; uStatus
0x180003a03  call    cs:__imp_mciDriverNotify
0x180003a09  mov     [rdi+10h], r15
0x180003a0d  mov     rcx, [r14]; hwndCallback
0x180003a10  mov     r8d, 1; uStatus
0x180003a16  mov     edx, ebp; wDeviceID
0x180003a18  call    cs:__imp_mciDriverNotify
0x180003a1e  lea     rcx, CritSec; lpCriticalSection
0x180003a25  call    cs:__imp_LeaveCriticalSection
0x180003a2b  mov     rax, rbx
0x180003a2e  add     rsp, 28h
0x180003a32  pop     r15
0x180003a34  pop     r14
0x180003a36  pop     rdi
0x180003a37  pop     rsi
0x180003a38  pop     rbp
0x180003a39  pop     rbx
0x180003a3a  retn
```
