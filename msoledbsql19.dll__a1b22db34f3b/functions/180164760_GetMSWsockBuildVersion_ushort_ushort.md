# GetMSWsockBuildVersion(ushort *,ushort *)

- ea: `0x180164760`
- end: `0x180164aa1`
- name: `?GetMSWsockBuildVersion@@YAKPEAG0@Z`
- size: `833`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180163f60`

## callees

- `0x1800030c0`
- `0x180003d80`
- `0x180157620`
- `0x180164760`
- `0x1801a65e1`
- `0x1801a6a46`
- `0x1801a6a52`
- `0x1801a6a5e`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180164885`
- `KERNEL32!FreeLibrary` at `0x180164885`
- `KERNEL32!GetLastError` at `0x18016483a`
- `KERNEL32!GetLastError` at `0x1801648a8`
- `KERNEL32!GetLastError` at `0x180164986`
- `KERNEL32!GetLastError` at `0x18016483a`
- `KERNEL32!GetLastError` at `0x1801648a8`
- `KERNEL32!GetLastError` at `0x180164986`
- `KERNEL32!GetModuleFileNameW` at `0x18016481e`
- `KERNEL32!GetModuleFileNameW` at `0x18016481e`

## string_xrefs

- `0x1801647bb`: `mswsock.dll`
- `0x1801647ec`: `mswsock.dll`
- `0x180164863`: `mswsock.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetMSWsockBuildVersion(unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  HMODULE v8; // rax
  HMODULE v9; // rsi
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  DWORD FileVersionInfoSizeW_0; // eax
  DWORD v13; // ebx
  DWORD v14; // eax
  void *v15; // rax
  const void *v16; // rdi
  _WORD *v17; // rcx
  DWORD v19; // [rsp+28h] [rbp-260h]
  LPVOID lpBuffer; // [rsp+30h] [rbp-258h] BYREF
  DWORD dwHandle; // [rsp+38h] [rbp-250h] BYREF
  unsigned int puLen; // [rsp+3Ch] [rbp-24Ch] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-248h] BYREF

  dwHandle = 0;
  lpBuffer = 0;
  puLen = 0;
  memset_0(Filename, 0, 0x208u);
  v4 = -1;
  v8 = SNILoadSystemLibA("mswsock.dll", v5, v6, v7);
  v9 = v8;
  if ( v8 )
  {
    ModuleFileNameW = GetModuleFileNameW(v8, Filename, 0x104u);
    if ( ModuleFileNameW - 1 > 0x102 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = -1;
      if ( (bidGblFlags & 2) != 0 && off_180264410[0] )
      {
        v19 = LastError;
        bidTraceW(off_1802610C8[0], 227328, off_180264410[0], "mswsock.dll");
      }
    }
    else
    {
      Filename[ModuleFileNameW] = 0;
      v4 = 0;
    }
    FreeLibrary(v9);
    if ( !v4 )
    {
      FileVersionInfoSizeW_0 = GetFileVersionInfoSizeW_0(Filename, &dwHandle);
      v13 = FileVersionInfoSizeW_0;
      if ( FileVersionInfoSizeW_0 )
      {
        v15 = (void *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD))(*(_QWORD *)gpmo + 112LL))(
                        gpmo,
                        FileVersionInfoSizeW_0);
        v16 = v15;
        if ( v15 )
        {
          if ( GetFileVersionInfoW_0(Filename, dwHandle, v13, v15) )
          {
            if ( VerQueryValueW_0(v16, L"\\", &lpBuffer, &puLen) && puLen == 52 )
            {
              v17 = lpBuffer;
              *a1 = *((_WORD *)lpBuffer + 7);
              *a2 = v17[6];
              v4 = 0;
            }
            else
            {
              v4 = -1;
              if ( (bidGblFlags & 2) != 0 && off_180264430[0] && bidID != -1 )
                ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, DWORD))off_180248050[0])(
                  bidID,
                  off_1802610E8[0],
                  294912,
                  off_180264430[0],
                  0,
                  v19);
            }
          }
          else
          {
            v4 = GetLastError();
            if ( (bidGblFlags & 2) != 0 && off_180264428[0] )
              bidTraceW(off_1802610E0[0], 282624, off_180264428[0], v4);
          }
          (*(void (__fastcall **)(struct ISOSHost_MemObj *, const void *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v16);
        }
        else
        {
          v4 = 14;
          if ( (bidGblFlags & 2) != 0 && off_180264420[0] && bidID != -1 )
            ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, DWORD))off_180248050[0])(
              bidID,
              off_1802610D8[0],
              275456,
              off_180264420[0],
              0,
              v19);
        }
      }
      else
      {
        v14 = GetLastError();
        v4 = v14;
        if ( (bidGblFlags & 2) != 0 && off_180264418[0] )
          bidTraceW(off_1802610D0[0], 266240, off_180264418[0], v14);
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 && off_180264408[0] )
  {
    bidTraceW(off_1802610C0[0], 207872, off_180264408[0], "mswsock.dll");
  }
  return v4;
}

```

## disassembly

```asm
0x180164760  mov     [rsp+arg_10], rbx
0x180164765  mov     [rsp+arg_18], rbp
0x18016476a  push    rsi
0x18016476b  push    rdi
0x18016476c  push    r12
0x18016476e  push    r14
0x180164770  push    r15
0x180164772  sub     rsp, 260h
0x180164779  mov     rax, cs:__security_cookie
0x180164780  xor     rax, rsp
0x180164783  mov     [rsp+288h+var_38], rax
0x18016478b  mov     r15, rdx
0x18016478e  mov     r14, rcx
0x180164791  xor     ebp, ebp
0x180164793  mov     [rsp+288h+dwHandle], ebp
0x180164797  mov     [rsp+288h+lpBuffer], rbp
0x18016479c  mov     [rsp+288h+puLen], ebp
0x1801647a0  xor     edx, edx; Val
0x1801647a2  mov     r8d, 208h; Size
0x1801647a8  lea     rcx, [rsp+288h+Filename]; void *
0x1801647ad  call    memset_0
0x1801647b2  mov     r12d, 0FFFFFFFFh
0x1801647b8  mov     ebx, r12d
0x1801647bb  lea     rcx, aMswsockDll; "mswsock.dll"
0x1801647c2  call    SNILoadSystemLibA
0x1801647c7  mov     rsi, rax
0x1801647ca  test    rax, rax
0x1801647cd  jnz     short loc_180164810
0x1801647cf  test    byte ptr cs:_bidGblFlags, 2
0x1801647d6  jz      loc_180164A73
0x1801647dc  mov     rax, cs:off_180264408; "<GetFullPathToSystemDLL|ERR|SNI> Couldn"...
0x1801647e3  test    rax, rax
0x1801647e6  jz      loc_180164A73
0x1801647ec  lea     r9, aMswsockDll; "mswsock.dll"
0x1801647f3  mov     r8, cs:off_180264408; "<GetFullPathToSystemDLL|ERR|SNI> Couldn"...
0x1801647fa  mov     edx, 32C00h
0x1801647ff  mov     rcx, cs:off_1802610C0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164806  call    _bidTraceW
0x18016480b  jmp     loc_180164A73
0x180164810  mov     r8d, 104h; nSize
0x180164816  lea     rdx, [rsp+288h+Filename]; lpFilename
0x18016481b  mov     rcx, rsi; hModule
0x18016481e  call    cs:__imp_GetModuleFileNameW
0x180164824  mov     edi, eax
0x180164826  lea     ecx, [rdi-1]
0x180164829  cmp     ecx, 102h
0x18016482f  ja      short loc_18016483A
0x180164831  mov     [rsp+rdi*2+288h+Filename], bp
0x180164836  mov     ebx, ebp
0x180164838  jmp     short loc_180164882
0x18016483a  call    cs:__imp_GetLastError
0x180164840  test    eax, eax
0x180164842  cmovz   eax, r12d
0x180164846  test    byte ptr cs:_bidGblFlags, 2
0x18016484d  jz      short loc_180164882
0x18016484f  mov     rcx, cs:off_180264410; "<GetFullPathToSystemDLL|ERR|SNI> Invali"...
0x180164856  test    rcx, rcx
0x180164859  jz      short loc_180164882
0x18016485b  mov     [rsp+288h+var_260], eax
0x18016485f  mov     dword ptr [rsp+288h+var_268], edi
0x180164863  lea     r9, aMswsockDll; "mswsock.dll"
0x18016486a  mov     r8, cs:off_180264410; "<GetFullPathToSystemDLL|ERR|SNI> Invali"...
0x180164871  mov     edx, 37800h
0x180164876  mov     rcx, cs:off_1802610C8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016487d  call    _bidTraceW
0x180164882  mov     rcx, rsi; hLibModule
0x180164885  call    cs:__imp_FreeLibrary
0x18016488b  test    ebx, ebx
0x18016488d  jnz     loc_180164A73
0x180164893  lea     rdx, [rsp+288h+dwHandle]; lpdwHandle
0x180164898  lea     rcx, [rsp+288h+Filename]; lptstrFilename
0x18016489d  call    GetFileVersionInfoSizeW_0
0x1801648a2  mov     ebx, eax
0x1801648a4  test    eax, eax
0x1801648a6  jnz     short loc_1801648ED
0x1801648a8  call    cs:__imp_GetLastError
0x1801648ae  mov     ebx, eax
0x1801648b0  test    byte ptr cs:_bidGblFlags, 2
0x1801648b7  jz      loc_180164A73
0x1801648bd  mov     rcx, cs:off_180264418; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x1801648c4  test    rcx, rcx
0x1801648c7  jz      loc_180164A73
0x1801648cd  mov     r9d, eax
0x1801648d0  mov     r8, cs:off_180264418; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x1801648d7  mov     edx, 41000h
0x1801648dc  mov     rcx, cs:off_1802610D0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801648e3  call    _bidTraceW
0x1801648e8  jmp     loc_180164A73
0x1801648ed  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1801648f4  mov     rax, [rcx]
0x1801648f7  mov     rdx, rbx
0x1801648fa  mov     rax, [rax+70h]
0x1801648fe  call    cs:__guard_dispatch_icall_fptr
0x180164904  mov     rdi, rax
0x180164907  test    rax, rax
0x18016490a  jnz     short loc_18016496E
0x18016490c  mov     ebx, 0Eh
0x180164911  test    byte ptr cs:_bidGblFlags, 2
0x180164918  jz      loc_180164A73
0x18016491e  mov     rax, cs:off_180264420; "<GetMSWsockBuildVersion|ERR|SNI> Memory"...
0x180164925  test    rax, rax
0x180164928  jz      loc_180164A73
0x18016492e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180164936  jz      loc_180164A73
0x18016493c  mov     rax, cs:off_180248050
0x180164943  mov     [rsp+288h+var_268], rbp
0x180164948  mov     r9, cs:off_180264420; "<GetMSWsockBuildVersion|ERR|SNI> Memory"...
0x18016494f  mov     r8d, 43400h
0x180164955  mov     rdx, cs:off_1802610D8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016495c  mov     rcx, cs:_bidID
0x180164963  call    cs:__guard_dispatch_icall_fptr
0x180164969  jmp     loc_180164A73
0x18016496e  mov     r9, rdi; lpData
0x180164971  mov     r8d, ebx; dwLen
0x180164974  mov     edx, [rsp+288h+dwHandle]; dwHandle
0x180164978  lea     rcx, [rsp+288h+Filename]; lptstrFilename
0x18016497d  call    GetFileVersionInfoW_0
0x180164982  test    eax, eax
0x180164984  jnz     short loc_1801649CB
0x180164986  call    cs:__imp_GetLastError
0x18016498c  mov     ebx, eax
0x18016498e  test    byte ptr cs:_bidGblFlags, 2
0x180164995  jz      loc_180164A58
0x18016499b  mov     rax, cs:off_180264428; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x1801649a2  test    rax, rax
0x1801649a5  jz      loc_180164A58
0x1801649ab  mov     r9d, ebx
0x1801649ae  mov     r8, cs:off_180264428; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x1801649b5  mov     edx, 45000h
0x1801649ba  mov     rcx, cs:off_1802610E0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801649c1  call    _bidTraceW
0x1801649c6  jmp     loc_180164A58
0x1801649cb  lea     r9, [rsp+288h+puLen]; puLen
0x1801649d0  lea     r8, [rsp+288h+lpBuffer]; lplpBuffer
0x1801649d5  lea     rdx, asc_1801E51B0; "\\"
0x1801649dc  mov     rcx, rdi; pBlock
0x1801649df  call    VerQueryValueW_0
0x1801649e4  test    eax, eax
0x1801649e6  jz      short loc_180164A08
0x1801649e8  cmp     [rsp+288h+puLen], 34h ; '4'
0x1801649ed  jnz     short loc_180164A08
0x1801649ef  mov     rcx, [rsp+288h+lpBuffer]
0x1801649f4  movzx   eax, word ptr [rcx+0Eh]
0x1801649f8  mov     [r14], ax
0x1801649fc  movzx   eax, word ptr [rcx+0Ch]
0x180164a00  mov     [r15], ax
0x180164a04  mov     ebx, ebp
0x180164a06  jmp     short loc_180164A58
0x180164a08  mov     ebx, r12d
0x180164a0b  test    byte ptr cs:_bidGblFlags, 2
0x180164a12  jz      short loc_180164A58
0x180164a14  mov     rax, cs:off_180264430; "<GetMSWsockBuildVersion|ERR|SNI> VerQue"...
0x180164a1b  test    rax, rax
0x180164a1e  jz      short loc_180164A58
0x180164a20  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180164a28  jz      short loc_180164A58
0x180164a2a  mov     rax, cs:off_180248050
0x180164a31  mov     [rsp+288h+var_268], rbp
0x180164a36  mov     r9, cs:off_180264430; "<GetMSWsockBuildVersion|ERR|SNI> VerQue"...
0x180164a3d  mov     r8d, 48000h
0x180164a43  mov     rdx, cs:off_1802610E8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180164a4a  mov     rcx, cs:_bidID
0x180164a51  call    cs:__guard_dispatch_icall_fptr
0x180164a57  nop
0x180164a58  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180164a5f  mov     rax, [rcx]
0x180164a62  mov     rdx, rdi
0x180164a65  mov     rax, [rax+80h]
0x180164a6c  call    cs:__guard_dispatch_icall_fptr
0x180164a72  nop
0x180164a73  mov     eax, ebx
0x180164a75  mov     rcx, [rsp+288h+var_38]
0x180164a7d  xor     rcx, rsp; StackCookie
0x180164a80  call    __security_check_cookie
0x180164a85  lea     r11, [rsp+288h+var_28]
0x180164a8d  mov     rbx, [r11+40h]
0x180164a91  mov     rbp, [r11+48h]
0x180164a95  mov     rsp, r11
0x180164a98  pop     r15
0x180164a9a  pop     r14
0x180164a9c  pop     r12
0x180164a9e  pop     rdi
0x180164a9f  pop     rsi
0x180164aa0  retn
```
