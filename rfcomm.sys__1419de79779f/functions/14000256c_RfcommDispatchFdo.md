# RfcommDispatchFdo

- ea: `0x14000256c`
- end: `0x140002805`
- name: `RfcommDispatchFdo`
- size: `665`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001ec0`

## callees

- `0x1400011ac`
- `0x140001c34`
- `0x14000256c`
- `0x14000280c`
- `0x140002ac8`
- `0x140003bf4`
- `0x140004550`
- `0x140004b4c`
- `0x140004c5c`
- `0x140032148`
- `0x14003365c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000263f`
- `ntoskrnl!IofCompleteRequest` at `0x14000263f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002701`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002701`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400025f4`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400025f4`
- `ntoskrnl!IofCallDriver` at `0x1400026e7`
- `ntoskrnl!IofCallDriver` at `0x1400026e7`

## string_xrefs

- `0x1400025e4`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
__int64 __fastcall RfcommDispatchFdo(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  char *v4; // r14
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  unsigned int v9; // esi
  int v11; // edx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // eax

  v2 = *(_QWORD *)(a1 + 64);
  v4 = *(char **)(a2 + 184);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_cqq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      22,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      *v4,
      a1,
      a2);
  v6 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(v2 + 40),
         (PVOID)a2,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c",
         0x198u,
         0x20u);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v11 = (unsigned __int8)*v4;
    if ( *v4 )
    {
      if ( *v4 != 2 )
      {
        if ( *v4 != 14 )
        {
          if ( *v4 == 15 )
          {
            if ( *((_DWORD *)v4 + 6) == 1179788 )
            {
              if ( *((_DWORD *)v4 + 2) >= 4u )
              {
                v12 = 0;
                **(_DWORD **)(a2 + 24) = 3;
              }
              else
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v11,
                    15,
                    24,
                    (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
                v12 = -1073741811;
              }
              goto LABEL_35;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qD(
                WPP_GLOBAL_Control->DeviceExtension,
                v11,
                1,
                25,
                (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
                a2,
                *((_DWORD *)v4 + 6));
            goto LABEL_16;
          }
          if ( *v4 == 22 )
          {
            v13 = ProcessPowerRequest(a1, (IRP *)a2);
            goto LABEL_19;
          }
          if ( *v4 != 23 )
          {
            if ( *v4 == 27 )
              return ProcessPnpRequest(a1, a2);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qc(
                WPP_GLOBAL_Control->DeviceExtension,
                v11,
                v8,
                26,
                (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
                a2,
                *v4);
LABEL_16:
            v12 = -1073741808;
LABEL_35:
            RfcommCompleteFdoIrp((PVOID)a2);
            return v12;
          }
LABEL_18:
          ++*(_BYTE *)(a2 + 67);
          *(_QWORD *)(a2 + 184) += 72LL;
          v13 = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 88), (PIRP)a2);
LABEL_19:
          v12 = v13;
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 40), (PVOID)a2, 0x20u);
          return v12;
        }
        v12 = RfcommDispatchFdoControl(a1, a2);
        if ( v12 == -1073741637 )
          goto LABEL_18;
LABEL_34:
        if ( v12 != 259 )
          goto LABEL_35;
        return v12;
      }
      v14 = RfcommDispatchFdoClose(a1, a2);
    }
    else
    {
      v14 = RfcommDispatchFdoCreate(a1, a2);
    }
    v12 = v14;
    goto LABEL_34;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      5,
      23,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      a2,
      v6);
  *(_DWORD *)(a2 + 48) = v9;
  IofCompleteRequest((PIRP)a2, 2);
  return v9;
}

```

## disassembly

```asm
0x14000256c  push    rbx
0x14000256e  push    rbp
0x14000256f  push    rsi
0x140002570  push    rdi
0x140002571  push    r12
0x140002573  push    r13
0x140002575  push    r14
0x140002577  push    r15
0x140002579  sub     rsp, 48h
0x14000257d  mov     r15, [rcx+40h]
0x140002581  mov     rdi, rdx
0x140002584  mov     r14, [rdx+0B8h]
0x14000258b  mov     rbx, rcx
0x14000258e  lea     r12, WPP_RECORDER_INITIALIZED
0x140002595  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000259c  lea     r13, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400025a3  jz      short loc_1400025D5
0x1400025a5  mov     al, [r14]
0x1400025a8  mov     r9d, 16h
0x1400025ae  mov     [rsp+88h+var_50], rdx
0x1400025b3  mov     [rsp+88h+var_58], rcx
0x1400025b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025bf  mov     byte ptr [rsp+88h+var_60], al
0x1400025c3  lea     r8d, [r9-13h]
0x1400025c7  mov     qword ptr [rsp+88h+RemlockSize], r13
0x1400025cc  mov     rcx, [rcx+40h]
0x1400025d0  call    WPP_RECORDER_SF_cqq
0x1400025d5  lea     rbp, [r15+28h]
0x1400025d9  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x1400025e1  mov     rcx, rbp; RemoveLock
0x1400025e4  lea     r8, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400025eb  mov     r9d, 198h; Line
0x1400025f1  mov     rdx, rdi; Tag
0x1400025f4  call    cs:__imp_IoAcquireRemoveLockEx
0x1400025fb  nop     dword ptr [rax+rax+00h]
0x140002600  mov     esi, eax
0x140002602  test    eax, eax
0x140002604  jns     short loc_140002652
0x140002606  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000260d  jz      short loc_140002637
0x14000260f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002616  mov     r9d, 17h
0x14000261c  mov     dword ptr [rsp+88h+var_58], eax
0x140002620  mov     [rsp+88h+var_60], rdi
0x140002625  mov     qword ptr [rsp+88h+RemlockSize], r13
0x14000262a  mov     rcx, [rcx+40h]
0x14000262e  lea     r8d, [r9-12h]
0x140002632  call    WPP_RECORDER_SF_qD
0x140002637  mov     dl, 2; PriorityBoost
0x140002639  mov     [rdi+30h], esi
0x14000263c  mov     rcx, rdi; Irp
0x14000263f  call    cs:__imp_IofCompleteRequest
0x140002646  nop     dword ptr [rax+rax+00h]
0x14000264b  mov     eax, esi
0x14000264d  jmp     loc_1400027F3
0x140002652  movzx   edx, byte ptr [r14]
0x140002656  xor     esi, esi
0x140002658  mov     ecx, edx
0x14000265a  test    edx, edx
0x14000265c  jz      loc_1400027CF
0x140002662  sub     ecx, 2
0x140002665  jz      loc_1400027C2
0x14000266b  sub     ecx, 0Ch
0x14000266e  jz      loc_1400027A9
0x140002674  sub     ecx, 1
0x140002677  jz      loc_14000271F
0x14000267d  sub     ecx, 7
0x140002680  jz      loc_140002712
0x140002686  sub     ecx, 1
0x140002689  jz      short loc_1400026D5
0x14000268b  cmp     ecx, 4
0x14000268e  jz      short loc_1400026C5
0x140002690  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002697  jz      short loc_1400026BB
0x140002699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026a0  lea     r9d, [rsi+1Ah]
0x1400026a4  mov     byte ptr [rsp+88h+var_58], dl
0x1400026a8  mov     [rsp+88h+var_60], rdi
0x1400026ad  mov     qword ptr [rsp+88h+RemlockSize], r13
0x1400026b2  mov     rcx, [rcx+40h]
0x1400026b6  call    WPP_RECORDER_SF_qc
0x1400026bb  mov     ebx, 0C0000010h
0x1400026c0  jmp     loc_1400027E4
0x1400026c5  mov     rdx, rdi
0x1400026c8  mov     rcx, rbx
0x1400026cb  call    ProcessPnpRequest
0x1400026d0  jmp     loc_1400027F3
0x1400026d5  inc     byte ptr [rdi+43h]
0x1400026d8  mov     rdx, rdi; Irp
0x1400026db  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400026e3  mov     rcx, [r15+58h]; DeviceObject
0x1400026e7  call    cs:__imp_IofCallDriver
0x1400026ee  nop     dword ptr [rax+rax+00h]
0x1400026f3  mov     r8d, 20h ; ' '; RemlockSize
0x1400026f9  mov     rdx, rdi; Tag
0x1400026fc  mov     rcx, rbp; RemoveLock
0x1400026ff  mov     ebx, eax
0x140002701  call    cs:__imp_IoReleaseRemoveLockEx
0x140002708  nop     dword ptr [rax+rax+00h]
0x14000270d  jmp     loc_1400027F1
0x140002712  mov     rdx, rdi
0x140002715  mov     rcx, rbx
0x140002718  call    ProcessPowerRequest
0x14000271d  jmp     short loc_1400026F3
0x14000271f  mov     eax, [r14+18h]
0x140002723  cmp     eax, 12008Ch
0x140002728  jz      short loc_140002760
0x14000272a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002731  jz      short loc_1400026BB
0x140002733  mov     rcx, cs:WPP_GLOBAL_Control
0x14000273a  mov     r9d, 19h
0x140002740  mov     dword ptr [rsp+88h+var_58], eax
0x140002744  mov     [rsp+88h+var_60], rdi
0x140002749  mov     qword ptr [rsp+88h+RemlockSize], r13
0x14000274e  mov     rcx, [rcx+40h]
0x140002752  lea     r8d, [r9-18h]
0x140002756  call    WPP_RECORDER_SF_qD
0x14000275b  jmp     loc_1400026BB
0x140002760  cmp     dword ptr [r14+8], 4
0x140002765  jnb     short loc_140002796
0x140002767  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000276e  jz      short loc_14000278F
0x140002770  mov     rcx, cs:WPP_GLOBAL_Control
0x140002777  mov     r9d, 18h
0x14000277d  mov     qword ptr [rsp+88h+RemlockSize], r13
0x140002782  mov     rcx, [rcx+40h]
0x140002786  lea     r8d, [r9-9]
0x14000278a  call    WPP_RECORDER_SF_
0x14000278f  mov     ebx, 0C000000Dh
0x140002794  jmp     short loc_1400027E4
0x140002796  mov     rax, [rdi+18h]
0x14000279a  mov     esi, 4
0x14000279f  xor     ebx, ebx
0x1400027a1  mov     dword ptr [rax], 3
0x1400027a7  jmp     short loc_1400027E4
0x1400027a9  mov     rdx, rdi
0x1400027ac  mov     rcx, rbx
0x1400027af  call    RfcommDispatchFdoControl
0x1400027b4  mov     ebx, eax
0x1400027b6  cmp     eax, 0C00000BBh
0x1400027bb  jnz     short loc_1400027DC
0x1400027bd  jmp     loc_1400026D5
0x1400027c2  mov     rdx, rdi
0x1400027c5  mov     rcx, rbx
0x1400027c8  call    RfcommDispatchFdoClose
0x1400027cd  jmp     short loc_1400027DA
0x1400027cf  mov     rdx, rdi
0x1400027d2  mov     rcx, rbx
0x1400027d5  call    RfcommDispatchFdoCreate
0x1400027da  mov     ebx, eax
0x1400027dc  cmp     ebx, 103h
0x1400027e2  jz      short loc_1400027F1
0x1400027e4  mov     r8, rsi
0x1400027e7  mov     edx, ebx
0x1400027e9  mov     rcx, rdi; Tag
0x1400027ec  call    RfcommCompleteFdoIrp
0x1400027f1  mov     eax, ebx
0x1400027f3  add     rsp, 48h
0x1400027f7  pop     r15
0x1400027f9  pop     r14
0x1400027fb  pop     r13
0x1400027fd  pop     r12
0x1400027ff  pop     rdi
0x140002800  pop     rsi
0x140002801  pop     rbp
0x140002802  pop     rbx
0x140002803  retn
```
