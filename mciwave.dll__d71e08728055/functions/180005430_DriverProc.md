# DriverProc

- ea: `0x180005430`
- end: `0x180005629`
- name: `DriverProc`
- size: `505`
- prototype: `__int64 __usercall@<rax>(DWORD_PTR dwDriverIdentifier@<rcx>, HDRVR hdrvr@<rdx>, LPARAM dwInitParam)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003614`
- `0x180005430`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800055dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800055dc`
- `USER32!DialogBoxParamW` at `0x18000550d`
- `USER32!DialogBoxParamW` at `0x18000550d`
- `WINMM!mciLoadCommandResource` at `0x1800055f7`
- `WINMM!mciLoadCommandResource` at `0x1800055f7`
- `WINMM!mciFreeCommandResource` at `0x18000552e`
- `WINMM!mciFreeCommandResource` at `0x18000552e`
- `WINMM!DefDriverProc` at `0x1800054d9`
- `WINMM!DefDriverProc` at `0x1800054d9`
- `WINMM!waveInGetNumDevs` at `0x1800055ba`
- `WINMM!waveInGetNumDevs` at `0x1800055ba`
- `WINMM!waveOutGetNumDevs` at `0x1800055ae`
- `WINMM!waveOutGetNumDevs` at `0x1800055ae`

## pseudocode

```c
LRESULT __fastcall DriverProc(DWORD_PTR dwDriverIdentifier, HDRVR hdrvr, UINT a3, HWND a4, int *dwInitParam)
{
  LRESULT result; // rax
  unsigned int v6; // ebx
  _WORD *v7; // r8
  int v8; // eax
  __int64 v9; // rbx
  WCHAR Buffer[32]; // [rsp+30h] [rbp-68h] BYREF

  switch ( a3 )
  {
    case 1u:
      cWaveOutMax = waveOutGetNumDevs();
      cWaveInMax = waveInGetNumDevs();
      v9 = 0;
      if ( LoadStringW(hModuleInstance, 2u, Buffer, 32) )
      {
        wTableEntry = mciLoadCommandResource(hModuleInstance, Buffer, 0);
        return wTableEntry != -1;
      }
      return v9;
    case 3u:
      v6 = 0;
      if ( (_DWORD)dwInitParam )
      {
        v7 = *(_WORD **)(dwInitParam + 1);
        if ( !v7 )
          goto LABEL_27;
        while ( (unsigned __int16)(*v7 - 48) <= 9u )
        {
          v8 = (unsigned __int16)*v7++;
          v6 = v8 + 2 * (5 * v6 - 24);
          if ( v6 >= 9 )
          {
            if ( v6 > 9 )
              goto LABEL_27;
            break;
          }
        }
        if ( v6 < 2 )
LABEL_27:
          v6 = 4;
        dwInitParam[3] = wTableEntry;
        result = *dwInitParam;
        wAudioSeconds = v6;
        dwInitParam[4] = 522;
      }
      else
      {
        return 10000;
      }
      break;
    case 4u:
      return 1;
    case 6u:
      if ( wTableEntry != -1 )
      {
        mciFreeCommandResource(wTableEntry);
        wTableEntry = -1;
      }
      return 1;
    case 7u:
      if ( (_DWORD)dwInitParam && (_DWORD)a4 && *dwInitParam == 20 )
        return (int)DialogBoxParamW(hModuleInstance, (LPCWSTR)1, a4, ConfigDlgProc, (LPARAM)dwInitParam);
      else
        return 0;
    default:
      if ( a3 != 8 && a3 - 9 >= 2 )
      {
        if ( WORD1(dwDriverIdentifier) || a3 - 2048 > 0xFFF )
          return DefDriverProc((unsigned int)dwDriverIdentifier, hdrvr, a3, (LPARAM)a4, (LPARAM)dwInitParam);
        else
          return mciDriverEntry((unsigned __int16)dwDriverIdentifier);
      }
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180005430  push    rbx
0x180005432  push    rdi
0x180005433  sub     rsp, 88h
0x18000543a  mov     rax, cs:__security_cookie
0x180005441  xor     rax, rsp
0x180005444  mov     [rsp+98h+var_28], rax
0x180005449  mov     eax, r8d
0x18000544c  mov     rdi, rdx
0x18000544f  mov     rdx, [rsp+98h+dwInitParam]
0x180005457  mov     r10, r9
0x18000545a  mov     r11d, r8d
0x18000545d  sub     eax, 1
0x180005460  jz      loc_1800055AE
0x180005466  sub     eax, 2
0x180005469  jz      loc_180005544
0x18000546f  sub     eax, 1
0x180005472  jz      loc_18000553A
0x180005478  sub     eax, 2
0x18000547b  jz      loc_180005521
0x180005481  sub     eax, 1
0x180005484  jz      short loc_1800054E4
0x180005486  sub     eax, 1
0x180005489  jz      loc_18000553A
0x18000548f  sub     eax, 1
0x180005492  jz      loc_18000553A
0x180005498  cmp     eax, 1
0x18000549b  jz      loc_18000553A
0x1800054a1  mov     eax, ecx
0x1800054a3  shr     eax, 10h
0x1800054a6  test    ax, ax
0x1800054a9  jnz     short loc_1800054CF
0x1800054ab  lea     eax, [r8-800h]
0x1800054b2  cmp     eax, 0FFFh
0x1800054b7  ja      short loc_1800054CF
0x1800054b9  mov     r9, rdx
0x1800054bc  movzx   ecx, cx; wDeviceID
0x1800054bf  mov     edx, r11d
0x1800054c2  mov     r8d, r10d
0x1800054c5  call    mciDriverEntry
0x1800054ca  jmp     loc_180005612
0x1800054cf  mov     [rsp+98h+lParam2], rdx; lParam2
0x1800054d4  mov     rdx, rdi; hdrvr
0x1800054d7  mov     ecx, ecx; dwDriverIdentifier
0x1800054d9  call    cs:__imp_DefDriverProc
0x1800054df  jmp     loc_180005612
0x1800054e4  test    edx, edx
0x1800054e6  jz      short loc_18000551A
0x1800054e8  test    r10d, r10d
0x1800054eb  jz      short loc_18000551A
0x1800054ed  cmp     dword ptr [rdx], 14h
0x1800054f0  jnz     short loc_18000551A
0x1800054f2  mov     rcx, cs:hModuleInstance; hInstance
0x1800054f9  lea     r9, ConfigDlgProc; lpDialogFunc
0x180005500  mov     [rsp+98h+lParam2], rdx; dwInitParam
0x180005505  mov     r8, r10; hWndParent
0x180005508  mov     edx, 1; lpTemplateName
0x18000550d  call    cs:__imp_DialogBoxParamW
0x180005513  cdqe
0x180005515  jmp     loc_180005612
0x18000551a  xor     eax, eax
0x18000551c  jmp     loc_180005612
0x180005521  mov     ecx, cs:wTableEntry; wTable
0x180005527  or      edi, 0FFFFFFFFh
0x18000552a  cmp     ecx, edi
0x18000552c  jz      short loc_18000553A
0x18000552e  call    cs:__imp_mciFreeCommandResource
0x180005534  mov     cs:wTableEntry, edi
0x18000553a  mov     eax, 1
0x18000553f  jmp     loc_180005612
0x180005544  xor     ebx, ebx
0x180005546  test    edx, edx
0x180005548  jnz     short loc_180005554
0x18000554a  mov     eax, 2710h
0x18000554f  jmp     loc_180005612
0x180005554  mov     r8, [rdx+4]
0x180005558  test    r8, r8
0x18000555b  jz      short loc_18000558E
0x18000555d  mov     r9d, 9
0x180005563  movzx   eax, word ptr [r8]
0x180005567  sub     ax, 30h ; '0'
0x18000556b  cmp     ax, r9w
0x18000556f  ja      short loc_180005589
0x180005571  movzx   eax, word ptr [r8]
0x180005575  lea     ebx, [rbx+rbx*4]
0x180005578  lea     ebx, [rbx-18h]
0x18000557b  add     r8, 2
0x18000557f  lea     ebx, [rax+rbx*2]
0x180005582  cmp     ebx, r9d
0x180005585  jb      short loc_180005563
0x180005587  ja      short loc_18000558E
0x180005589  cmp     ebx, 2
0x18000558c  jnb     short loc_180005593
0x18000558e  mov     ebx, 4
0x180005593  mov     eax, cs:wTableEntry
0x180005599  mov     [rdx+0Ch], eax
0x18000559c  movsxd  rax, dword ptr [rdx]
0x18000559f  mov     cs:wAudioSeconds, ebx
0x1800055a5  mov     dword ptr [rdx+10h], 20Ah
0x1800055ac  jmp     short loc_180005612
0x1800055ae  call    cs:__imp_waveOutGetNumDevs
0x1800055b4  mov     cs:cWaveOutMax, eax
0x1800055ba  call    cs:__imp_waveInGetNumDevs
0x1800055c0  mov     rcx, cs:hModuleInstance; hInstance
0x1800055c7  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x1800055cc  mov     r9d, 20h ; ' '; cchBufferMax
0x1800055d2  mov     cs:cWaveInMax, eax
0x1800055d8  lea     edx, [r9-1Eh]; uID
0x1800055dc  call    cs:__imp_LoadStringW
0x1800055e2  xor     ebx, ebx
0x1800055e4  test    eax, eax
0x1800055e6  jz      short loc_18000560F
0x1800055e8  mov     rcx, cs:hModuleInstance; hInstance
0x1800055ef  lea     rdx, [rsp+98h+Buffer]; lpResName
0x1800055f4  xor     r8d, r8d; wType
0x1800055f7  call    cs:__imp_mciLoadCommandResource
0x1800055fd  or      edi, 0FFFFFFFFh
0x180005600  mov     cs:wTableEntry, eax
0x180005606  cmp     eax, edi
0x180005608  jz      short loc_18000560F
0x18000560a  mov     ebx, 1
0x18000560f  mov     rax, rbx
0x180005612  mov     rcx, [rsp+98h+var_28]
0x180005617  xor     rcx, rsp; StackCookie
0x18000561a  call    __security_check_cookie
0x18000561f  add     rsp, 88h
0x180005626  pop     rdi
0x180005627  pop     rbx
0x180005628  retn
```
