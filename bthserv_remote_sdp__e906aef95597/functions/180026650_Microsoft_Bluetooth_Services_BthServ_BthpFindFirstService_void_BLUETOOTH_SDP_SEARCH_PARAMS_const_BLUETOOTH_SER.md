# Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(void *,_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)

- ea: `0x180026650`
- end: `0x1800267ff`
- name: `?BthpFindFirstService@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z`
- size: `431`
- prototype: `Microsoft::Bluetooth::Services::BthServ *__fastcall(__int64, __int64, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800247d0`

## callees

- `0x180016aac`
- `0x180024c84`
- `0x180024f34`
- `0x180026650`
- `0x180026c70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002667b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026710`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002667b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026710`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026724`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026724`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800266d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800266d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800267d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800267d2`

## pseudocode

```c
Microsoft::Bluetooth::Services::BthServ *__fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(
        __int64 a1,
        __int64 a2,
        void *a3,
        int a4)
{
  Microsoft::Bluetooth::Services::BthServ *v7; // rbp
  HANDLE ProcessHeap; // rax
  void *v9; // rdx
  Microsoft::Bluetooth::Services::BthServ *v10; // rdi
  ULONG v11; // esi
  DWORD L2CapSdpRecords; // ebx
  HANDLE v13; // rax
  Microsoft::Bluetooth::Services::BthServ *v14; // rax
  Microsoft::Bluetooth::Services::BthServ *v15; // r15
  __int64 v16; // rcx
  unsigned int *v17; // r9
  HANDLE v18; // rax
  struct _BLUETOOTH_SDP_RECORD *v19; // r14
  struct _BLUETOOTH_SDP_RECORD *v20; // rax
  struct _BLUETOOTH_SERVICE_RECORD *v21; // r8
  __int64 v23; // [rsp+60h] [rbp+8h] BYREF

  v23 = a1;
  v7 = 0;
  ProcessHeap = GetProcessHeap();
  v10 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(ProcessHeap, 8u, 0x18u);
  v11 = 512;
  L2CapSdpRecords = v10 == 0 ? 0xE : 0;
  while ( !L2CapSdpRecords || L2CapSdpRecords == 122 )
  {
    v13 = GetProcessHeap();
    v14 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(v13, 0, v11);
    v15 = v14;
    if ( !v14 )
    {
      L2CapSdpRecords = 14;
      break;
    }
    v16 = *(_QWORD *)(a2 + 8);
    LODWORD(v23) = 0;
    L2CapSdpRecords = BthServGetL2CapSdpRecords((unsigned __int64 *)(v16 + 8), a4, (ULONG *)&v23, v14, v11);
    if ( !L2CapSdpRecords )
    {
      v19 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v15 + (unsigned int)v23);
      *(_QWORD *)v10 = v15;
      *((_QWORD *)v10 + 2) = v19;
      *((_QWORD *)v10 + 1) = v15;
      if ( (*(_BYTE *)v15 & 0xF8) == 0x30 )
      {
        LODWORD(v23) = 0;
        v20 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(v15, v19, (unsigned __int32 *)&v23, v17);
        *((_QWORD *)v10 + 1) = v20;
        if ( v20 )
        {
          if ( v20 != v19 )
          {
            v7 = v10;
            if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(v10, a3, v21) )
            {
              if ( v10 )
                goto LABEL_19;
            }
            else
            {
              L2CapSdpRecords = GetLastError();
              v7 = 0;
            }
          }
        }
      }
      break;
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v15);
    if ( L2CapSdpRecords != 122 )
      break;
    v11 = v23;
    if ( ((a4 - 1) & 0xFFFFFFFD) == 0 )
      a4 = 2;
  }
  if ( v10 )
    Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(v10, v9);
LABEL_19:
  SetLastError(L2CapSdpRecords);
  return v7;
}

```

## disassembly

```asm
0x180026650  mov     rax, rsp
0x180026653  mov     [rax+10h], rbx
0x180026657  mov     [rax+18h], rbp
0x18002665b  mov     [rax+20h], rsi
0x18002665f  mov     [rax+8], rcx
0x180026663  push    rdi
0x180026664  push    r12
0x180026666  push    r13
0x180026668  push    r14
0x18002666a  push    r15
0x18002666c  sub     rsp, 30h
0x180026670  mov     r14d, r9d
0x180026673  mov     r12, r8
0x180026676  mov     r13, rdx
0x180026679  xor     ebp, ebp
0x18002667b  call    cs:__imp_GetProcessHeap
0x180026682  nop     dword ptr [rax+rax+00h]
0x180026687  mov     rcx, rax; hHeap
0x18002668a  lea     edx, [rbp+8]; dwFlags
0x18002668d  lea     r8d, [rbp+18h]; dwBytes
0x180026691  call    cs:__imp_HeapAlloc
0x180026698  nop     dword ptr [rax+rax+00h]
0x18002669d  mov     rdi, rax
0x1800266a0  mov     esi, 200h
0x1800266a5  neg     rax
0x1800266a8  sbb     ebx, ebx
0x1800266aa  not     ebx
0x1800266ac  and     ebx, 0Eh
0x1800266af  test    ebx, ebx
0x1800266b1  jz      short loc_1800266BC
0x1800266b3  cmp     ebx, 7Ah ; 'z'
0x1800266b6  jnz     loc_1800267C3
0x1800266bc  call    cs:__imp_GetProcessHeap
0x1800266c3  nop     dword ptr [rax+rax+00h]
0x1800266c8  mov     r8d, esi; dwBytes
0x1800266cb  xor     edx, edx; dwFlags
0x1800266cd  mov     rcx, rax; hHeap
0x1800266d0  call    cs:__imp_HeapAlloc
0x1800266d7  nop     dword ptr [rax+rax+00h]
0x1800266dc  mov     r15, rax
0x1800266df  test    rax, rax
0x1800266e2  jz      loc_1800267BE
0x1800266e8  mov     rcx, [r13+8]
0x1800266ec  lea     r8, [rsp+58h+arg_0]
0x1800266f1  and     dword ptr [rsp+58h+arg_0], ebp
0x1800266f5  add     rcx, 8
0x1800266f9  mov     r9, rax
0x1800266fc  mov     [rsp+58h+var_38], esi
0x180026700  mov     edx, r14d
0x180026703  call    ?BthServGetL2CapSdpRecords@@YAKPEA_KW4_BTHSERV_QUERY_TYPE@@PEAKPEAEK@Z; BthServGetL2CapSdpRecords(unsigned __int64 *,_BTHSERV_QUERY_TYPE,ulong *,uchar *,ulong)
0x180026708  mov     ebx, eax
0x18002670a  mov     esi, eax
0x18002670c  test    eax, eax
0x18002670e  jz      short loc_180026755
0x180026710  call    cs:__imp_GetProcessHeap
0x180026717  nop     dword ptr [rax+rax+00h]
0x18002671c  mov     r8, r15; lpMem
0x18002671f  xor     edx, edx; dwFlags
0x180026721  mov     rcx, rax; hHeap
0x180026724  call    cs:__imp_HeapFree
0x18002672b  nop     dword ptr [rax+rax+00h]
0x180026730  cmp     ebx, 7Ah ; 'z'
0x180026733  jnz     loc_1800267C3
0x180026739  mov     esi, dword ptr [rsp+58h+arg_0]
0x18002673d  lea     eax, [r14-1]
0x180026741  test    eax, 0FFFFFFFDh
0x180026746  jnz     loc_1800266AF
0x18002674c  lea     r14d, [rbx-78h]
0x180026750  jmp     loc_1800266AF
0x180026755  mov     r14d, dword ptr [rsp+58h+arg_0]
0x18002675a  mov     rcx, r15; this
0x18002675d  add     r14, r15
0x180026760  mov     [rdi], r15
0x180026763  mov     [rdi+10h], r14
0x180026767  mov     [rdi+8], r15
0x18002676b  mov     al, [r15]
0x18002676e  and     al, 0F8h
0x180026770  cmp     al, 30h ; '0'
0x180026772  jnz     short loc_1800267C3
0x180026774  and     dword ptr [rsp+58h+arg_0], ebp
0x180026778  lea     r8, [rsp+58h+arg_0]; void *
0x18002677d  mov     rdx, r14; struct _BLUETOOTH_SDP_RECORD *
0x180026780  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180026785  mov     [rdi+8], rax
0x180026789  test    rax, rax
0x18002678c  jz      short loc_1800267C3
0x18002678e  cmp     rax, r14
0x180026791  jz      short loc_1800267C3
0x180026793  mov     rdx, r12; void *
0x180026796  mov     rcx, rdi; this
0x180026799  mov     rbp, rdi
0x18002679c  call    ?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)
0x1800267a1  test    eax, eax
0x1800267a3  jnz     short loc_1800267B7
0x1800267a5  call    cs:__imp_GetLastError
0x1800267ac  nop     dword ptr [rax+rax+00h]
0x1800267b1  mov     ebx, eax
0x1800267b3  xor     ebp, ebp
0x1800267b5  jmp     short loc_1800267C3
0x1800267b7  test    rdi, rdi
0x1800267ba  jnz     short loc_1800267D0
0x1800267bc  jmp     short loc_1800267C3
0x1800267be  mov     ebx, 0Eh
0x1800267c3  test    rdi, rdi
0x1800267c6  jz      short loc_1800267D0
0x1800267c8  mov     rcx, rdi; this
0x1800267cb  call    ?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)
0x1800267d0  mov     ecx, ebx; dwErrCode
0x1800267d2  call    cs:__imp_SetLastError
0x1800267d9  nop     dword ptr [rax+rax+00h]
0x1800267de  mov     rbx, [rsp+58h+arg_8]
0x1800267e3  mov     rax, rbp
0x1800267e6  mov     rbp, [rsp+58h+arg_10]
0x1800267eb  mov     rsi, [rsp+58h+arg_18]
0x1800267f0  add     rsp, 30h
0x1800267f4  pop     r15
0x1800267f6  pop     r14
0x1800267f8  pop     r13
0x1800267fa  pop     r12
0x1800267fc  pop     rdi
0x1800267fd  retn
```
