# PcFilterStatus

- ea: `0x140001d40`
- end: `0x140001fe3`
- name: `PcFilterStatus`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001d40`
- `0x1400023d0`
- `0x140002484`
- `0x14000eca0`
- `0x14000ee88`
- `0x140011800`
- `0x140011a8c`

## import_xrefs

- `NDIS!NdisFIndicateStatus` at `0x140001d82`
- `NDIS!NdisFIndicateStatus` at `0x140001ef2`
- `NDIS!NdisFIndicateStatus` at `0x140001f4f`
- `NDIS!NdisFIndicateStatus` at `0x140001d82`
- `NDIS!NdisFIndicateStatus` at `0x140001ef2`
- `NDIS!NdisFIndicateStatus` at `0x140001f4f`
- `NDIS!NdisReleaseRWLock` at `0x140001ec8`
- `NDIS!NdisReleaseRWLock` at `0x140001f1a`
- `NDIS!NdisReleaseRWLock` at `0x140001ec8`
- `NDIS!NdisReleaseRWLock` at `0x140001f1a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140001dec`
- `NDIS!NdisAcquireRWLockWrite` at `0x140001dec`

## pseudocode

```c
void __fastcall PcFilterStatus(__int64 a1, struct _NDIS_STATUS_INDICATION *a2)
{
  unsigned __int64 v4; // rbp
  __int64 v5; // rsi
  int v6; // r12d
  char v7; // r8
  unsigned __int64 v8; // rbp
  int v9; // r15d
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  struct _NDIS_RW_LOCK_EX *v12; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF

  if ( (unsigned int)(*(_DWORD *)(a1 + 24) - 1) <= 3 )
  {
    switch ( a2->StatusCode )
    {
      case 0x40010008:
        PcpFilterStatusWanLineUp();
        break;
      case 0x40010009:
        PcpFilterStatusWanLineDown(a1, a2);
        break;
      case 0x40010017:
        v4 = *((_QWORD *)a2->StatusBuffer + 2);
        if ( v4 != -1 )
        {
          v5 = *(_QWORD *)(a1 + 160);
          *(_WORD *)&LockState.OldIrql = 0;
          LockState.Flags = 0;
          NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v5 + 16), &LockState, 0);
          if ( *(_DWORD *)(v5 + 244) )
          {
            v6 = *(_DWORD *)(v5 + 308);
            v7 = 0;
            v8 = v4 >> 3;
            v9 = *(_DWORD *)(v5 + 304);
            if ( v5 != -296 )
              *(_QWORD *)(v5 + 24) = *(_QWORD *)(v5 + 296);
            if ( ((*(_DWORD *)(v5 + 232) >> 1) & 1) != 0 )
            {
              v7 = 1;
              *(_DWORD *)(v5 + 232) &= ~2u;
            }
            if ( v8 && v8 != *(_QWORD *)(v5 + 32) )
            {
              *(_QWORD *)(v5 + 32) = v8;
              v7 = 1;
            }
            if ( v7 )
            {
              QosLineComputeControlInterval(v5 + 24);
              QosLineComputeBufferSizes(v5 + 24);
              v10 = *(_QWORD *)(v5 + 120);
              if ( !v10 || v10 == *(_QWORD *)(v5 + 32) )
                v11 = 0;
              else
                v11 = v10 * (unsigned __int64)*(unsigned int *)(v5 + 140) / 0xF4240;
              *(_QWORD *)(v5 + 216) = v11;
            }
            v12 = *(struct _NDIS_RW_LOCK_EX **)(v5 + 16);
            *(_DWORD *)(v5 + 304) = v9;
            *(_DWORD *)(v5 + 308) = v6;
            NdisReleaseRWLock(v12, &LockState);
          }
          else
          {
            NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 16), &LockState);
          }
        }
        NdisFIndicateStatus(*(NDIS_HANDLE *)(a1 + 40), a2);
        break;
      case 0x40030036:
        if ( ((*(_DWORD *)(a1 + 20) - 1) & 0xFFFFFFF7) == 0 )
        {
          PcpHandleDot11DSCPToUPMappingIndication(a1 + 214, a2->StatusBuffer);
          NdisFIndicateStatus(*(NDIS_HANDLE *)(a1 + 40), a2);
        }
        break;
      default:
        NdisFIndicateStatus(*(NDIS_HANDLE *)(a1 + 40), a2);
        break;
    }
  }
}

```

## disassembly

```asm
0x140001d40  push    rbx
0x140001d42  push    rdi
0x140001d43  sub     rsp, 68h
0x140001d47  mov     eax, [rcx+18h]
0x140001d4a  mov     rdi, rdx
0x140001d4d  dec     eax
0x140001d4f  mov     rbx, rcx
0x140001d52  cmp     eax, 3
0x140001d55  ja      short loc_140001D8E
0x140001d57  mov     eax, [rdx+14h]
0x140001d5a  sub     eax, 40010008h
0x140001d5f  jz      loc_140001FD9
0x140001d65  sub     eax, 1
0x140001d68  jz      loc_140001FCF
0x140001d6e  sub     eax, 0Eh
0x140001d71  jz      short loc_140001D96
0x140001d73  cmp     eax, 2001Fh
0x140001d78  jz      loc_140001F28
0x140001d7e  mov     rcx, [rcx+28h]; NdisFilterHandle
0x140001d82  call    cs:__imp_NdisFIndicateStatus
0x140001d89  nop     dword ptr [rax+rax+00h]
0x140001d8e  add     rsp, 68h
0x140001d92  pop     rdi
0x140001d93  pop     rbx
0x140001d94  retn
0x140001d96  mov     rax, [rdx+30h]
0x140001d9a  mov     [rsp+78h+arg_8], rbp
0x140001da2  mov     rbp, [rax+10h]
0x140001da6  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140001daa  jz      loc_140001EEB
0x140001db0  xor     eax, eax
0x140001db2  mov     [rsp+78h+arg_10], rsi
0x140001dba  mov     rsi, [rcx+0A0h]
0x140001dc1  lea     rdx, [rsp+78h+LockState]; LockState
0x140001dc9  xorps   xmm0, xmm0
0x140001dcc  mov     word ptr [rsp+78h+LockState.OldIrql], ax
0x140001dd4  xor     r8d, r8d; Flags
0x140001dd7  mov     [rsp+78h+LockState.Flags], al
0x140001dde  movups  [rsp+78h+var_48], xmm0
0x140001de3  mov     rcx, [rsi+10h]; Lock
0x140001de7  movups  [rsp+78h+var_38], xmm0
0x140001dec  call    cs:__imp_NdisAcquireRWLockWrite
0x140001df3  nop     dword ptr [rax+rax+00h]
0x140001df8  cmp     dword ptr [rsi+0F4h], 0
0x140001dff  jz      loc_140001F0E
0x140001e05  mov     [rsp+78h+var_18], r12
0x140001e0a  lea     rax, [rsi+128h]
0x140001e11  mov     r12d, [rsi+134h]
0x140001e18  xor     r8b, r8b
0x140001e1b  shr     rbp, 3
0x140001e1f  mov     [rsp+78h+var_20], r14
0x140001e24  mov     [rsp+78h+var_28], r15
0x140001e29  mov     r15d, [rsi+130h]
0x140001e30  test    rax, rax
0x140001e33  jz      short loc_140001E3C
0x140001e35  mov     rax, [rax]
0x140001e38  mov     [rsi+18h], rax
0x140001e3c  mov     edx, [rsi+0E8h]
0x140001e42  mov     eax, edx
0x140001e44  shr     eax, 1
0x140001e46  bt      eax, 0
0x140001e4a  jb      loc_140001F60
0x140001e50  test    rbp, rbp
0x140001e53  jz      short loc_140001E62
0x140001e55  cmp     rbp, [rsi+20h]
0x140001e59  jz      short loc_140001E62
0x140001e5b  mov     [rsi+20h], rbp
0x140001e5f  mov     r8b, 1
0x140001e62  mov     rcx, qword ptr [rsp+78h+var_38]
0x140001e67  lea     rax, [rcx-1]
0x140001e6b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001e6f  jbe     loc_140001F71
0x140001e75  mov     edx, dword ptr [rsp+78h+var_48+8]
0x140001e79  test    edx, edx
0x140001e7b  jnz     loc_140001F7D
0x140001e81  test    r8b, r8b
0x140001e84  jz      short loc_140001EAE
0x140001e86  lea     rcx, [rsi+18h]
0x140001e8a  call    QosLineComputeControlInterval
0x140001e8f  lea     rcx, [rsi+18h]
0x140001e93  call    QosLineComputeBufferSizes
0x140001e98  mov     rax, [rsi+78h]
0x140001e9c  test    rax, rax
0x140001e9f  jnz     loc_140001FA5
0x140001ea5  xor     edx, edx
0x140001ea7  mov     [rsi+0D8h], rdx
0x140001eae  mov     rcx, [rsi+10h]; Lock
0x140001eb2  lea     rdx, [rsp+78h+LockState]; LockState
0x140001eba  mov     [rsi+130h], r15d
0x140001ec1  mov     [rsi+134h], r12d
0x140001ec8  call    cs:__imp_NdisReleaseRWLock
0x140001ecf  nop     dword ptr [rax+rax+00h]
0x140001ed4  mov     r15, [rsp+78h+var_28]
0x140001ed9  mov     r14, [rsp+78h+var_20]
0x140001ede  mov     r12, [rsp+78h+var_18]
0x140001ee3  mov     rsi, [rsp+78h+arg_10]
0x140001eeb  mov     rcx, [rbx+28h]; NdisFilterHandle
0x140001eef  mov     rdx, rdi; StatusIndication
0x140001ef2  call    cs:__imp_NdisFIndicateStatus
0x140001ef9  nop     dword ptr [rax+rax+00h]
0x140001efe  mov     rbp, [rsp+78h+arg_8]
0x140001f06  add     rsp, 68h
0x140001f0a  pop     rdi
0x140001f0b  pop     rbx
0x140001f0c  retn
0x140001f0e  mov     rcx, [rsi+10h]; Lock
0x140001f12  lea     rdx, [rsp+78h+LockState]; LockState
0x140001f1a  call    cs:__imp_NdisReleaseRWLock
0x140001f21  nop     dword ptr [rax+rax+00h]
0x140001f26  jmp     short loc_140001EE3
0x140001f28  mov     eax, [rcx+14h]
0x140001f2b  dec     eax
0x140001f2d  test    eax, 0FFFFFFF7h
0x140001f32  jnz     loc_140001D8E
0x140001f38  mov     rdx, [rdx+30h]
0x140001f3c  add     rcx, 0D6h
0x140001f43  call    PcpHandleDot11DSCPToUPMappingIndication
0x140001f48  mov     rcx, [rbx+28h]; NdisFilterHandle
0x140001f4c  mov     rdx, rdi; StatusIndication
0x140001f4f  call    cs:__imp_NdisFIndicateStatus
0x140001f56  nop     dword ptr [rax+rax+00h]
0x140001f5b  jmp     loc_140001D8E
0x140001f60  and     edx, 0FFFFFFFDh
0x140001f63  mov     r8b, 1
0x140001f66  mov     [rsi+0E8h], edx
0x140001f6c  jmp     loc_140001E50
0x140001f71  mov     [rsi+78h], rcx
0x140001f75  mov     r8b, 1
0x140001f78  jmp     loc_140001E75
0x140001f7d  mov     eax, dword ptr [rsp+78h+var_48+4]
0x140001f81  lea     rcx, [rsi+18h]
0x140001f85  mov     r8d, dword ptr [rsp+78h+var_48+0Ch]
0x140001f8a  mov     r9d, dword ptr [rsp+78h+var_48]
0x140001f8f  mov     [rsp+78h+var_58], eax
0x140001f93  call    QosLineUpdateTotalWeight
0x140001f98  test    eax, eax
0x140001f9a  js      loc_140001EAE
0x140001fa0  jmp     loc_140001E86
0x140001fa5  cmp     rax, [rsi+20h]
0x140001fa9  jz      loc_140001EA5
0x140001faf  mov     ecx, [rsi+8Ch]
0x140001fb5  imul    rcx, rax
0x140001fb9  mov     rax, 431BDE82D7B634DBh
0x140001fc3  mul     rcx
0x140001fc6  shr     rdx, 12h
0x140001fca  jmp     loc_140001EA7
0x140001fcf  call    PcpFilterStatusWanLineDown
0x140001fd4  jmp     loc_140001D8E
0x140001fd9  call    PcpFilterStatusWanLineUp
0x140001fde  jmp     loc_140001D8E
```
