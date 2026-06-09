# DeRefQueryBlobEx

- ea: `0x1800317e0`
- end: `0x180031b45`
- name: `DeRefQueryBlobEx`
- size: `869`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `28`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001c000`
- `0x18001e740`
- `0x180023fc4`
- `0x180024680`
- `0x180024a10`
- `0x18002cf9c`
- `0x180030aec`
- `0x180030ea8`
- `0x18003229c`
- `0x180032348`
- `0x180034dc0`
- `0x180047b80`
- `0x180047d98`
- `0x180047f4c`
- `0x1800493e0`
- `0x1800498e4`
- `0x180049998`
- `0x180049e58`
- `0x18004a910`
- `0x180053258`
- `0x180062450`
- `0x180073c00`
- `0x180078720`
- `0x180079dd4`
- `0x180084da0`
- `0x180092560`
- `0x180092f48`
- `0x180093184`

## callees

- `0x1800120f0`
- `0x18002b050`
- `0x18002e894`
- `0x1800317e0`
- `0x180053474`
- `0x1800669f8`
- `0x18006e84c`
- `0x180072b60`
- `0x18007d72c`
- `0x180083954`
- `0x180084c4c`
- `0x1800de6cc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003188f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003188f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031ab9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031b2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031b2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003199e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003199e`

## pseudocode

```c
void __fastcall DeRefQueryBlobEx(char *lpMem, __int64 a2, char a3, int a4)
{
  __int64 v4; // rsi
  signed __int32 v8; // edi
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  struct _TP_TIMER *v19; // rcx
  _OWORD *v20; // rdi
  void *v21; // rcx
  __int64 v22; // rcx
  HMODULE v23; // rcx
  LPCSTR retaddr; // [rsp+78h] [rbp+0h]

  v4 = a4;
  if ( g_fVelocitySuppressInternalExports && !g_DnsIsCache && !(unsigned int)Dns_IsCallerDns(retaddr) )
    goto LABEL_54;
  if ( lpMem )
  {
    if ( !*(_DWORD *)lpMem )
    {
LABEL_54:
      MicrosoftTelemetryAssertTriggeredNoArgs(lpMem);
      return;
    }
    _InterlockedIncrement16((volatile signed __int16 *)&lpMem[2 * v4 + 60]);
    v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem);
    if ( (BYTE3(xmmword_1801119E0) & 4) != 0 )
      WPP_SF_lsdqd((_DWORD)lpMem, 15, a3, v4, a2, a3, (__int64)lpMem, v8);
    if ( !v8 )
    {
      if ( !*((_DWORD *)lpMem + 86) )
        MicrosoftTelemetryAssertTriggeredNoArgs(lpMem);
      if ( *((char **)lpMem + 19) != lpMem + 152 )
        MicrosoftTelemetryAssertTriggeredNoArgs(lpMem);
      v9 = (void *)*((_QWORD *)lpMem + 412);
      if ( v9 )
      {
        DnsApiFree(v9);
        *((_QWORD *)lpMem + 412) = 0;
      }
      v10 = (void *)*((_QWORD *)lpMem + 410);
      if ( v10 )
      {
        CloseHandle(v10);
        *((_QWORD *)lpMem + 410) = 0;
      }
      v11 = (void *)*((_QWORD *)lpMem + 146);
      if ( v11 )
      {
        CloseHandle(v11);
        *((_QWORD *)lpMem + 146) = 0;
      }
      Query_RemoveFromGlobalList(lpMem);
      if ( *((char **)lpMem + 17) != lpMem + 136 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v12);
      v13 = (void *)*((_QWORD *)lpMem + 102);
      if ( v13 )
        Dns_RecordListFree(v13);
      v14 = (void *)*((_QWORD *)lpMem + 103);
      if ( v14 )
        Dns_RecordListFree(v14);
      v15 = (void *)*((_QWORD *)lpMem + 107);
      if ( v15 )
        Dns_RecordListFree(v15);
      v16 = (void *)*((_QWORD *)lpMem + 108);
      if ( v16 )
        Dns_RecordListFree(v16);
      Packet_FreeMsgBuf(*((LPVOID *)lpMem + 144));
      v17 = (void *)*((_QWORD *)lpMem + 120);
      *((_QWORD *)lpMem + 144) = 0;
      Dns_RecordListFree(v17);
      v18 = (void *)*((_QWORD *)lpMem + 145);
      *((_QWORD *)lpMem + 120) = 0;
      Dns_FreeMsgBufRpc(v18);
      v19 = (struct _TP_TIMER *)*((_QWORD *)lpMem + 433);
      *((_QWORD *)lpMem + 145) = 0;
      if ( v19 )
      {
        ThreadPool_DeleteTimer(v19);
        *((_QWORD *)lpMem + 433) = 0;
      }
      v20 = lpMem + 976;
      if ( lpMem != (char *)-976LL )
      {
        DnsApiFree(*((LPVOID *)lpMem + 126));
        *((_QWORD *)lpMem + 126) = 0;
        *((_DWORD *)lpMem + 251) = 0;
        if ( *(_WORD *)v20 )
        {
          *v20 = 0;
          *(_OWORD *)(lpMem + 988) = 0;
        }
      }
      if ( *((_WORD *)lpMem + 328) || *((_QWORD *)lpMem + 86) || *((_DWORD *)lpMem + 171) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v19);
      v21 = (void *)*((_QWORD *)lpMem + 62);
      if ( v21 )
        DeRefNetworkQueryBlob(v21);
      DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 184));
      ResolverDeRefServerMapView(*((_QWORD *)lpMem + 432));
      *((_QWORD *)lpMem + 432) = 0;
      if ( *((_QWORD *)lpMem + 71) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v22);
      if ( *((_QWORD *)lpMem + 72) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v22);
      DnsApiFree(*((LPVOID *)lpMem + 28));
      v23 = (HMODULE)*((_QWORD *)lpMem + 40);
      *((_QWORD *)lpMem + 28) = 0;
      if ( v23 )
      {
        FreeLibrary(v23);
        *((_QWORD *)lpMem + 40) = 0;
      }
      if ( *((_DWORD *)lpMem + 119) && (*((_DWORD *)lpMem + 264) || *((_QWORD *)lpMem + 133)) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v23);
      DnsApiFree(lpMem);
    }
  }
}

```

## disassembly

```asm
0x1800317e0  push    rbx
0x1800317e2  push    rbp
0x1800317e3  push    rsi
0x1800317e4  push    rdi
0x1800317e5  push    r14
0x1800317e7  push    r15
0x1800317e9  sub     rsp, 48h
0x1800317ed  xor     r15d, r15d
0x1800317f0  movsxd  rsi, r9d
0x1800317f3  cmp     cs:g_fVelocitySuppressInternalExports, r15d
0x1800317fa  mov     ebp, r8d
0x1800317fd  mov     r14, rdx
0x180031800  mov     rbx, rcx
0x180031803  jnz     loc_180031A58
0x180031809  test    rbx, rbx
0x18003180c  jz      short loc_180031837
0x18003180e  cmp     [rbx], r15d
0x180031811  jz      loc_180031A81
0x180031817  lock inc word ptr [rbx+rsi*2+3Ch]
0x18003181d  or      edi, 0FFFFFFFFh
0x180031820  lock xadd [rbx], edi
0x180031824  dec     edi
0x180031826  test    byte ptr cs:xmmword_1801119E0+3, 4
0x18003182d  jnz     loc_180031A8B
0x180031833  test    edi, edi
0x180031835  jz      short loc_180031845
0x180031837  add     rsp, 48h
0x18003183b  pop     r15
0x18003183d  pop     r14
0x18003183f  pop     rdi
0x180031840  pop     rsi
0x180031841  pop     rbp
0x180031842  pop     rbx
0x180031843  retn
0x180031845  cmp     [rbx+158h], r15d
0x18003184c  jz      loc_180031AAF
0x180031852  lea     rax, [rbx+98h]
0x180031859  cmp     [rax], rax
0x18003185c  jz      short loc_180031863
0x18003185e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031863  mov     rcx, [rbx+0CE0h]; lpMem
0x18003186a  test    rcx, rcx
0x18003186d  jnz     loc_180031A2A
0x180031873  mov     rcx, [rbx+0CD0h]; hObject
0x18003187a  test    rcx, rcx
0x18003187d  jnz     loc_180031AB9
0x180031883  mov     rcx, [rbx+490h]; hObject
0x18003188a  test    rcx, rcx
0x18003188d  jz      short loc_1800318A2
0x18003188f  call    cs:__imp_CloseHandle
0x180031896  nop     dword ptr [rax+rax+00h]
0x18003189b  mov     [rbx+490h], r15
0x1800318a2  mov     rcx, rbx
0x1800318a5  call    Query_RemoveFromGlobalList
0x1800318aa  lea     rax, [rbx+88h]
0x1800318b1  cmp     [rax], rax
0x1800318b4  jnz     loc_180031A10
0x1800318ba  mov     rcx, [rbx+330h]; lpMem
0x1800318c1  test    rcx, rcx
0x1800318c4  jnz     loc_180031AD1
0x1800318ca  mov     rcx, [rbx+338h]; lpMem
0x1800318d1  test    rcx, rcx
0x1800318d4  jnz     loc_180031ADB
0x1800318da  mov     rcx, [rbx+358h]; lpMem
0x1800318e1  test    rcx, rcx
0x1800318e4  jnz     loc_180031AE5
0x1800318ea  mov     rcx, [rbx+360h]; lpMem
0x1800318f1  test    rcx, rcx
0x1800318f4  jnz     loc_180031AEF
0x1800318fa  mov     rcx, [rbx+480h]; lpMem
0x180031901  call    Packet_FreeMsgBuf
0x180031906  mov     rcx, [rbx+3C0h]; lpMem
0x18003190d  mov     [rbx+480h], r15
0x180031914  call    Dns_RecordListFree
0x180031919  mov     rcx, [rbx+488h]; lpMem
0x180031920  mov     [rbx+3C0h], r15
0x180031927  call    Dns_FreeMsgBufRpc
0x18003192c  mov     rcx, [rbx+0D88h]; pti
0x180031933  mov     [rbx+488h], r15
0x18003193a  test    rcx, rcx
0x18003193d  jnz     loc_180031AF9
0x180031943  lea     rdi, [rbx+3D0h]
0x18003194a  test    rdi, rdi
0x18003194d  jz      short loc_18003196A
0x18003194f  mov     rcx, [rdi+20h]; lpMem
0x180031953  call    DnsApiFree
0x180031958  mov     [rdi+20h], r15
0x18003195c  mov     [rdi+1Ch], r15d
0x180031960  cmp     [rdi], r15w
0x180031964  jnz     loc_180031B0A
0x18003196a  cmp     [rbx+290h], r15w
0x180031972  jnz     short loc_180031981
0x180031974  cmp     [rbx+2B0h], r15
0x18003197b  jz      loc_180031A3B
0x180031981  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031986  mov     rcx, [rbx+1F0h]; lpMem
0x18003198d  test    rcx, rcx
0x180031990  jz      short loc_180031997
0x180031992  call    DeRefNetworkQueryBlob
0x180031997  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18003199e  call    cs:__imp_DeleteCriticalSection
0x1800319a5  nop     dword ptr [rax+rax+00h]
0x1800319aa  mov     rcx, [rbx+0D80h]
0x1800319b1  call    ResolverDeRefServerMapView
0x1800319b6  mov     [rbx+0D80h], r15
0x1800319bd  cmp     [rbx+238h], r15
0x1800319c4  jnz     loc_180031B19
0x1800319ca  cmp     [rbx+240h], r15
0x1800319d1  jnz     loc_180031B23
0x1800319d7  mov     rcx, [rbx+0E0h]; lpMem
0x1800319de  call    DnsApiFree
0x1800319e3  mov     rcx, [rbx+140h]; hLibModule
0x1800319ea  mov     [rbx+0E0h], r15
0x1800319f1  test    rcx, rcx
0x1800319f4  jnz     loc_180031B2D
0x1800319fa  cmp     [rbx+1DCh], r15d
0x180031a01  jnz     short loc_180031A1A
0x180031a03  mov     rcx, rbx; lpMem
0x180031a06  call    DnsApiFree
0x180031a0b  jmp     loc_180031837
0x180031a10  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031a15  jmp     loc_1800318BA
0x180031a1a  cmp     [rbx+420h], r15d
0x180031a21  jz      short loc_180031A4D
0x180031a23  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031a28  jmp     short loc_180031A03
0x180031a2a  call    DnsApiFree
0x180031a2f  mov     [rbx+0CE0h], r15
0x180031a36  jmp     loc_180031873
0x180031a3b  cmp     [rbx+2ACh], r15d
0x180031a42  jz      loc_180031986
0x180031a48  jmp     loc_180031981
0x180031a4d  cmp     [rbx+428h], r15
0x180031a54  jz      short loc_180031A03
0x180031a56  jmp     short loc_180031A23
0x180031a58  cmp     cs:g_DnsIsCache, r15d
0x180031a5f  jnz     loc_180031809
0x180031a65  mov     rcx, [rsp+78h]; lpModuleName
0x180031a6a  call    Dns_IsCallerDns
0x180031a6f  test    eax, eax
0x180031a71  jnz     loc_180031809
0x180031a77  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031a7c  jmp     loc_180031837
0x180031a81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031a86  jmp     loc_180031837
0x180031a8b  mov     [rsp+78h+var_40], edi
0x180031a8f  mov     edx, 0Fh
0x180031a94  mov     [rsp+78h+var_48], rbx
0x180031a99  mov     r9d, esi
0x180031a9c  mov     [rsp+78h+var_50], ebp
0x180031aa0  mov     [rsp+78h+var_58], r14
0x180031aa5  call    WPP_SF_lsdqd
0x180031aaa  jmp     loc_180031833
0x180031aaf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031ab4  jmp     loc_180031852
0x180031ab9  call    cs:__imp_CloseHandle
0x180031ac0  nop     dword ptr [rax+rax+00h]
0x180031ac5  mov     [rbx+0CD0h], r15
0x180031acc  jmp     loc_180031883
0x180031ad1  call    Dns_RecordListFree
0x180031ad6  jmp     loc_1800318CA
0x180031adb  call    Dns_RecordListFree
0x180031ae0  jmp     loc_1800318DA
0x180031ae5  call    Dns_RecordListFree
0x180031aea  jmp     loc_1800318EA
0x180031aef  call    Dns_RecordListFree
0x180031af4  jmp     loc_1800318FA
0x180031af9  call    ThreadPool_DeleteTimer
0x180031afe  mov     [rbx+0D88h], r15
0x180031b05  jmp     loc_180031943
0x180031b0a  xorps   xmm0, xmm0
0x180031b0d  movups  xmmword ptr [rdi], xmm0
0x180031b10  movups  xmmword ptr [rdi+0Ch], xmm0
0x180031b14  jmp     loc_18003196A
0x180031b19  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031b1e  jmp     loc_1800319CA
0x180031b23  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031b28  jmp     loc_1800319D7
0x180031b2d  call    cs:__imp_FreeLibrary
0x180031b34  nop     dword ptr [rax+rax+00h]
0x180031b39  mov     [rbx+140h], r15
0x180031b40  jmp     loc_1800319FA
```
