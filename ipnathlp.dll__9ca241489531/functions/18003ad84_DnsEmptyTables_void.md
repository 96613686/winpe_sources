# DnsEmptyTables(void)

- ea: `0x18003ad84`
- end: `0x18003af99`
- name: `?DnsEmptyTables@@YAXXZ`
- size: `533`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800251f8`
- `0x18003062c`
- `0x18003ab00`
- `0x18004bf70`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18003ad84`
- `0x180064258`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aefd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aefd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aee0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003af0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aee0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003af0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003add5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003add5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003af58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003af58`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003aebe`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003aef7`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003af47`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003aebe`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003aef7`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003af47`
- `ntdll!RtlGetElementGenericTable` at `0x18003ae36`
- `ntdll!RtlGetElementGenericTable` at `0x18003af37`
- `ntdll!RtlGetElementGenericTable` at `0x18003ae36`
- `ntdll!RtlGetElementGenericTable` at `0x18003af37`
- `ntdll!RtlNumberGenericTableElements` at `0x18003ade2`
- `ntdll!RtlNumberGenericTableElements` at `0x18003af20`
- `ntdll!RtlNumberGenericTableElements` at `0x18003ade2`
- `ntdll!RtlNumberGenericTableElements` at `0x18003af20`

## pseudocode

```c
void DnsEmptyTables(void)
{
  ULONG v0; // eax
  ULONG v1; // esi
  _QWORD *ElementGenericTable; // rax
  __int64 v3; // rbx
  _DWORD *v4; // r15
  void **v5; // r14
  unsigned int v6; // edx
  void *v7; // rdi
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax
  ULONG v11; // ebx
  PVOID v12; // rax
  __int128 Buffer; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
  Buffer = 0;
  EnterCriticalSection(&DnsTableLock);
  v0 = RtlNumberGenericTableElements(&g_DnsTable);
  v1 = v0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids, v0);
  }
  while ( v1 )
  {
    ElementGenericTable = RtlGetElementGenericTable(&g_DnsTable, --v1);
    v3 = 0;
    *((_QWORD *)&Buffer + 1) = 0;
    v4 = ElementGenericTable;
    v5 = (void **)(ElementGenericTable + 2);
    if ( *((_DWORD *)ElementGenericTable + 2) )
    {
      do
      {
        v6 = *((_DWORD *)*v5 + 3 * v3);
        LODWORD(Buffer) = v6;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned __int8)Buffer,
            BYTE2(v6),
            (unsigned int)v3,
            (unsigned __int8)Buffer,
            BYTE1(v6),
            BYTE2(v6),
            HIBYTE(v6));
        }
        RtlDeleteElementGenericTable(&g_ReverseDnsTable, &Buffer);
        v3 = (unsigned int)(v3 + 1);
      }
      while ( (unsigned int)v3 < v4[2] );
    }
    v7 = *(void **)v4;
    v8 = *v5;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *v5 = 0;
    RtlDeleteElementGenericTable(&g_DnsTable, v4);
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v7);
  }
  v11 = RtlNumberGenericTableElements(&g_ReverseDnsTable);
  while ( v11 )
  {
    v12 = RtlGetElementGenericTable(&g_ReverseDnsTable, --v11);
    RtlDeleteElementGenericTable(&g_ReverseDnsTable, v12);
  }
  LeaveCriticalSection(&DnsTableLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
}

```

## disassembly

```asm
0x18003ad84  push    rbx
0x18003ad86  push    rsi
0x18003ad87  push    rdi
0x18003ad88  push    r13
0x18003ad8a  push    r14
0x18003ad8c  push    r15
0x18003ad8e  sub     rsp, 58h
0x18003ad92  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad99  lea     r13, WPP_GLOBAL_Control
0x18003ada0  cmp     rcx, r13
0x18003ada3  jz      short loc_18003ADC6
0x18003ada5  test    byte ptr [rcx+1Ch], 10h
0x18003ada9  jz      short loc_18003ADC6
0x18003adab  cmp     byte ptr [rcx+19h], 6
0x18003adaf  jb      short loc_18003ADC6
0x18003adb1  mov     rcx, [rcx+10h]
0x18003adb5  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003adbc  mov     edx, 10h
0x18003adc1  call    WPP_SF_
0x18003adc6  xorps   xmm0, xmm0
0x18003adc9  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003add0  movups  [rsp+88h+Buffer], xmm0
0x18003add5  call    cs:__imp_EnterCriticalSection
0x18003addb  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003ade2  call    cs:__imp_RtlNumberGenericTableElements
0x18003ade8  mov     esi, eax
0x18003adea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003adf1  cmp     rcx, r13
0x18003adf4  jz      loc_18003AF11
0x18003adfa  test    byte ptr [rcx+1Ch], 10h
0x18003adfe  jz      loc_18003AF11
0x18003ae04  cmp     byte ptr [rcx+19h], 5
0x18003ae08  jb      loc_18003AF11
0x18003ae0e  mov     rcx, [rcx+10h]
0x18003ae12  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003ae19  mov     edx, 11h
0x18003ae1e  mov     r9d, eax
0x18003ae21  call    WPP_SF_d
0x18003ae26  jmp     loc_18003AF11
0x18003ae2b  dec     esi
0x18003ae2d  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003ae34  mov     edx, esi; I
0x18003ae36  call    cs:__imp_RtlGetElementGenericTable
0x18003ae3c  xor     ebx, ebx
0x18003ae3e  mov     qword ptr [rsp+88h+Buffer+8], 0
0x18003ae47  mov     r15, rax
0x18003ae4a  lea     r14, [rax+10h]
0x18003ae4e  cmp     [rax+8], ebx
0x18003ae51  jbe     short loc_18003AECC
0x18003ae53  mov     rax, [r14]
0x18003ae56  lea     rcx, [rbx+rbx*2]
0x18003ae5a  mov     edx, [rax+rcx*4]
0x18003ae5d  mov     dword ptr [rsp+88h+Buffer], edx
0x18003ae61  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae68  cmp     rcx, r13
0x18003ae6b  jz      short loc_18003AEB2
0x18003ae6d  test    byte ptr [rcx+1Ch], 10h
0x18003ae71  jz      short loc_18003AEB2
0x18003ae73  cmp     byte ptr [rcx+19h], 5
0x18003ae77  jb      short loc_18003AEB2
0x18003ae79  mov     rcx, [rcx+10h]
0x18003ae7d  mov     eax, edx
0x18003ae7f  mov     r9d, edx
0x18003ae82  shr     eax, 10h
0x18003ae85  shr     r9d, 18h
0x18003ae89  mov     [rsp+88h+var_50], r9d
0x18003ae8e  mov     r9d, ebx
0x18003ae91  shr     edx, 8
0x18003ae94  movzx   r8d, al
0x18003ae98  movzx   eax, dl
0x18003ae9b  movzx   edx, byte ptr [rsp+88h+Buffer]
0x18003aea0  mov     [rsp+88h+var_58], r8d
0x18003aea5  mov     [rsp+88h+var_60], eax
0x18003aea9  mov     [rsp+88h+var_68], edx
0x18003aead  call    WPP_SF_dDDDD
0x18003aeb2  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18003aeb7  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003aebe  call    cs:__imp_RtlDeleteElementGenericTable
0x18003aec4  inc     ebx
0x18003aec6  cmp     ebx, [r15+8]
0x18003aeca  jb      short loc_18003AE53
0x18003aecc  mov     rdi, [r15]
0x18003aecf  mov     rbx, [r14]
0x18003aed2  call    cs:__imp_GetProcessHeap
0x18003aed8  mov     r8, rbx; lpMem
0x18003aedb  xor     edx, edx; dwFlags
0x18003aedd  mov     rcx, rax; hHeap
0x18003aee0  call    cs:__imp_HeapFree
0x18003aee6  mov     rdx, r15; Buffer
0x18003aee9  mov     qword ptr [r14], 0
0x18003aef0  lea     rcx, ?g_DnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003aef7  call    cs:__imp_RtlDeleteElementGenericTable
0x18003aefd  call    cs:__imp_GetProcessHeap
0x18003af03  mov     r8, rdi; lpMem
0x18003af06  xor     edx, edx; dwFlags
0x18003af08  mov     rcx, rax; hHeap
0x18003af0b  call    cs:__imp_HeapFree
0x18003af11  test    esi, esi
0x18003af13  jnz     loc_18003AE2B
0x18003af19  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003af20  call    cs:__imp_RtlNumberGenericTableElements
0x18003af26  mov     ebx, eax
0x18003af28  test    eax, eax
0x18003af2a  jz      short loc_18003AF51
0x18003af2c  dec     ebx
0x18003af2e  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003af35  mov     edx, ebx; I
0x18003af37  call    cs:__imp_RtlGetElementGenericTable
0x18003af3d  mov     rdx, rax; Buffer
0x18003af40  lea     rcx, ?g_ReverseDnsTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18003af47  call    cs:__imp_RtlDeleteElementGenericTable
0x18003af4d  test    ebx, ebx
0x18003af4f  jnz     short loc_18003AF2C
0x18003af51  lea     rcx, ?DnsTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003af58  call    cs:__imp_LeaveCriticalSection
0x18003af5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af65  cmp     rcx, r13
0x18003af68  jz      short loc_18003AF8B
0x18003af6a  test    byte ptr [rcx+1Ch], 10h
0x18003af6e  jz      short loc_18003AF8B
0x18003af70  cmp     byte ptr [rcx+19h], 6
0x18003af74  jb      short loc_18003AF8B
0x18003af76  mov     rcx, [rcx+10h]
0x18003af7a  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18003af81  mov     edx, 13h
0x18003af86  call    WPP_SF_
0x18003af8b  add     rsp, 58h
0x18003af8f  pop     r15
0x18003af91  pop     r14
0x18003af93  pop     r13
0x18003af95  pop     rdi
0x18003af96  pop     rsi
0x18003af97  pop     rbx
0x18003af98  retn
```
