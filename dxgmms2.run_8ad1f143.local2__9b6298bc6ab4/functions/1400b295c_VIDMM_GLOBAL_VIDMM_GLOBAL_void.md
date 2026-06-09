# VIDMM_GLOBAL::VIDMM_GLOBAL(void)

- ea: `0x1400b295c`
- end: `0x1400b2f1b`
- name: `??0VIDMM_GLOBAL@@QEAA@XZ`
- size: `1471`
- prototype: `VIDMM_GLOBAL *__fastcall(VIDMM_GLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400be918`

## callees

- `0x1400583dc`
- `0x140058ac0`
- `0x1400b295c`
- `0x1400b6050`
- `0x1400c31d4`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400b2eaa`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400b2eaa`
- `ntoskrnl!KeInitializeEvent` at `0x1400b2c18`
- `ntoskrnl!KeInitializeEvent` at `0x1400b2c91`
- `ntoskrnl!KeInitializeEvent` at `0x1400b2c18`
- `ntoskrnl!KeInitializeEvent` at `0x1400b2c91`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b2bc7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b2c4f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b2e71`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b2bc7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b2c4f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b2e71`

## pseudocode

```c
VIDMM_GLOBAL *__fastcall VIDMM_GLOBAL::VIDMM_GLOBAL(VIDMM_GLOBAL *this)
{
  __int64 v2; // rdx
  char *v3; // rcx
  __int64 v4; // rax

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_DWORD *)this + 178) = 0;
  *((_DWORD *)this + 179) = 13;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_BYTE *)this + 736) = 0;
  memset((char *)this + 737, 0, 0x40u);
  memset((char *)this + 2600, 0, 0x200u);
  *((_DWORD *)this + 779) = 0;
  *((_QWORD *)this + 390) = 0;
  *((_QWORD *)this + 391) = 0;
  *((_BYTE *)this + 3200) = 0;
  *((_BYTE *)this + 3202) = 0;
  *((_QWORD *)this + 501) = 0;
  *((_DWORD *)this + 1004) = 0;
  *((_QWORD *)this + 4505) = 0;
  *((_QWORD *)this + 4506) = 0;
  *((_DWORD *)this + 9014) = 0;
  *((_DWORD *)this + 9015) = 78;
  *((_DWORD *)this + 9016) = 71;
  *((_QWORD *)this + 4510) = (char *)this + 36072;
  *((_QWORD *)this + 4509) = (char *)this + 36072;
  *((_QWORD *)this + 4512) = (char *)this + 36088;
  *((_QWORD *)this + 4511) = (char *)this + 36088;
  *((_QWORD *)this + 4517) = 0;
  *((_QWORD *)this + 4518) = 0;
  *((_DWORD *)this + 9038) = 0;
  *((_DWORD *)this + 9039) = 1;
  *((_DWORD *)this + 9040) = -1;
  *((_DWORD *)this + 9062) = 0;
  *((_DWORD *)this + 9064) = 257;
  *((_BYTE *)this + 36260) = 0;
  *((_QWORD *)this + 4535) = 0;
  *((_QWORD *)this + 4536) = 0;
  *((_DWORD *)this + 9074) = 0;
  *((_DWORD *)this + 9075) = 12;
  *((_BYTE *)this + 36304) = 0;
  *((_QWORD *)this + 4539) = 0;
  *((_QWORD *)this + 4540) = 0;
  *((_QWORD *)this + 4551) = 0;
  *((_QWORD *)this + 4552) = 0;
  *((_DWORD *)this + 9106) = 0;
  *((_DWORD *)this + 9107) = 78;
  *((_DWORD *)this + 9108) = 46;
  *((_DWORD *)this + 9110) = -1;
  *((_QWORD *)this + 4556) = 0;
  *((_QWORD *)this + 4557) = 0;
  *((_QWORD *)this + 4558) = 0;
  *((_QWORD *)this + 4559) = 0;
  memset((char *)this + 36672, 0, 0x220u);
  *((_BYTE *)this + 37224) &= 0x9Du;
  *((_BYTE *)this + 37225) &= 0xF2u;
  *((_BYTE *)this + 37227) &= ~1u;
  *((_DWORD *)this + 9304) = 0;
  *((_WORD *)this + 18614) = 0;
  *((_BYTE *)this + 37233) = 0;
  *((_QWORD *)this + 4663) = 0;
  *((_QWORD *)this + 4664) = 0;
  *((_DWORD *)this + 9330) = 0;
  *((_DWORD *)this + 9331) = 1;
  DXGK_LOG::DXGK_LOG((VIDMM_GLOBAL *)((char *)this + 37328));
  *((_QWORD *)this + 4670) = 0;
  *((_DWORD *)this + 9342) = 0;
  *((_QWORD *)this + 4672) = 0;
  *((_QWORD *)this + 4673) = 0;
  *((_DWORD *)this + 9348) = 0;
  *((_DWORD *)this + 9349) = 22;
  *((_DWORD *)this + 9350) = 66;
  *((_QWORD *)this + 4677) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 4676);
  *((_QWORD *)this + 4680) = 0;
  *((_QWORD *)this + 4681) = 0;
  *((_DWORD *)this + 9364) = 0;
  *((_DWORD *)this + 9365) = 1;
  *((_DWORD *)this + 9370) = 0;
  *((_DWORD *)this + 9386) = 1;
  *((_QWORD *)this + 4684) = (char *)this + 37464;
  *((_QWORD *)this + 4683) = (char *)this + 37464;
  *((_QWORD *)this + 4691) = DXG_DEFERRED_WORK_QUEUE::DeferredWorkQueueCallback;
  *((_QWORD *)this + 4692) = (char *)this + 37440;
  *((_QWORD *)this + 4689) = 0;
  KeInitializeEvent((PRKEVENT)this + 1562, NotificationEvent, 1u);
  VIDMM_PURGE_TELEMETRY::VIDMM_PURGE_TELEMETRY((VIDMM_GLOBAL *)((char *)this + 37552), this);
  *((_DWORD *)this + 10178) = 0;
  *((_QWORD *)this + 5106) = (char *)this + 40840;
  *((_QWORD *)this + 5105) = (char *)this + 40840;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 5125);
  *((_QWORD *)this + 5126) = 0;
  *((_QWORD *)this + 5127) = 0;
  *((_QWORD *)this + 5128) = 0;
  *((_DWORD *)this + 10258) = 0;
  *((_DWORD *)this + 10259) = 1;
  *((_DWORD *)this + 10266) = 0;
  KeInitializeEvent((PRKEVENT)this + 1710, NotificationEvent, 1u);
  *((_QWORD *)this + 5135) = 0;
  *((_QWORD *)this + 5136) = 0;
  *((_QWORD *)this + 5137) = 0;
  *((_QWORD *)this + 5138) = 0;
  *((_QWORD *)this + 5139) = 0;
  *((_QWORD *)this + 5140) = 0;
  *((_QWORD *)this + 5141) = 0;
  *((_DWORD *)this + 10284) = 0;
  *((_DWORD *)this + 10285) = 1;
  *((_DWORD *)this + 10286) = -1;
  *((_QWORD *)this + 5144) = 0;
  *((_QWORD *)this + 5145) = 0;
  *((_DWORD *)this + 10292) = 0;
  *((_DWORD *)this + 10293) = 7;
  *((_DWORD *)this + 10294) = 60;
  *((_QWORD *)this + 5158) = 0;
  *((_QWORD *)this + 5159) = 0;
  *((_QWORD *)this + 5160) = 0;
  *((_QWORD *)this + 5161) = 0;
  *((_QWORD *)this + 5162) = 0;
  *((_BYTE *)this + 41304) = 0;
  *((_QWORD *)this + 5164) = 0;
  *((_QWORD *)this + 5165) = 0;
  *((_DWORD *)this + 10332) = 0;
  *((_DWORD *)this + 10333) = 78;
  *((_DWORD *)this + 10334) = -1;
  *((_BYTE *)this + 41344) = 0;
  *((_DWORD *)this + 10337) = -1;
  *((_BYTE *)this + 41368) = 0;
  *((_QWORD *)this + 5172) = 0;
  *((_QWORD *)this + 5173) = 0;
  *((_QWORD *)this + 5176) = 0;
  *((_QWORD *)this + 5177) = 0;
  *((_DWORD *)this + 10380) = 0;
  v2 = 0;
  *((_QWORD *)this + 5199) = 0;
  *((_QWORD *)this + 82) = (char *)this + 648;
  *((_QWORD *)this + 81) = (char *)this + 648;
  *((_QWORD *)this + 5088) = (char *)this + 40696;
  *((_QWORD *)this + 5087) = (char *)this + 40696;
  *((_QWORD *)this + 4679) = (char *)this + 37424;
  *((_QWORD *)this + 4678) = (char *)this + 37424;
  *((_QWORD *)this + 84) = (char *)this + 664;
  *((_QWORD *)this + 83) = (char *)this + 664;
  *((_QWORD *)this + 86) = (char *)this + 680;
  *((_QWORD *)this + 85) = (char *)this + 680;
  *((_QWORD *)this + 4516) = (char *)this + 36120;
  *((_QWORD *)this + 4515) = (char *)this + 36120;
  *((_QWORD *)this + 4514) = (char *)this + 36104;
  *((_QWORD *)this + 4513) = (char *)this + 36104;
  *((_QWORD *)this + 5157) = (char *)this + 41248;
  *((_QWORD *)this + 5156) = (char *)this + 41248;
  *((_QWORD *)this + 5170) = (char *)this + 41352;
  *((_QWORD *)this + 5169) = (char *)this + 41352;
  *((_QWORD *)this + 4534) = (char *)this + 36264;
  *((_QWORD *)this + 4533) = (char *)this + 36264;
  do
  {
    v3 = (char *)this + 16 * v2 + 41184;
    *((_QWORD *)this + 2 * v2 + 5149) = v3;
    v4 = 2 * (v2 + 2574);
    ++v2;
    *((_QWORD *)this + v4) = v3;
  }
  while ( v2 != 4 );
  *((_QWORD *)this + 401) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 5086);
  *((_DWORD *)this + 778) = 1;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 36544), 0, 0, 0, 0x20u, 0x61356956u, 0);
  *((_QWORD *)this + 5174) = 0;
  *((_QWORD *)this + 5112) = VidMmUpgrade64KBWork;
  *((_QWORD *)this + 5113) = this;
  *((_QWORD *)this + 5110) = 0;
  *((_QWORD *)this + 5114) = 2;
  *((_DWORD *)this + 10206) = 0x40000;
  InitializePeriodicTrimData((VIDMM_GLOBAL *)((char *)this + 36328));
  InitializePeriodicTrimData((VIDMM_GLOBAL *)((char *)this + 36368));
  return this;
}

```

## disassembly

```asm
0x1400b295c  mov     [rsp+arg_0], rbx
0x1400b2961  mov     [rsp+arg_8], r14
0x1400b2966  push    r15
0x1400b2968  sub     rsp, 40h
0x1400b296c  xor     r14d, r14d
0x1400b296f  mov     rbx, rcx
0x1400b2972  mov     [rcx], r14
0x1400b2975  xor     edx, edx; Val
0x1400b2977  mov     [rcx+8], r14d
0x1400b297b  mov     [rcx+0Ch], r14b
0x1400b297f  mov     [rcx+10h], r14
0x1400b2983  lea     r8d, [r14+40h]; Size
0x1400b2987  mov     [rcx+28h], r14d
0x1400b298b  mov     [rcx+38h], r14
0x1400b298f  mov     [rcx+2B8h], r14
0x1400b2996  mov     [rcx+2C0h], r14
0x1400b299d  mov     [rcx+2C8h], r14d
0x1400b29a4  mov     dword ptr [rcx+2CCh], 0Dh
0x1400b29ae  mov     [rcx+2D0h], r14
0x1400b29b5  mov     [rcx+2D8h], r14
0x1400b29bc  mov     [rcx+2E0h], r14b
0x1400b29c3  add     rcx, 2E1h; void *
0x1400b29ca  call    memset
0x1400b29cf  lea     rcx, [rbx+0A28h]; void *
0x1400b29d6  xor     edx, edx; Val
0x1400b29d8  mov     r8d, 200h; Size
0x1400b29de  call    memset
0x1400b29e3  mov     [rbx+0C2Ch], r14d
0x1400b29ea  lea     rax, [rbx+8CE8h]
0x1400b29f1  mov     [rbx+0C30h], r14
0x1400b29f8  lea     r15d, [r14+1]
0x1400b29fc  mov     [rbx+0C38h], r14
0x1400b2a03  lea     rcx, [rbx+8F40h]; void *
0x1400b2a0a  mov     [rbx+0C80h], r14b
0x1400b2a11  xor     edx, edx; Val
0x1400b2a13  mov     [rbx+0C82h], r14b
0x1400b2a1a  mov     r8d, 220h; Size
0x1400b2a20  mov     [rbx+0FA8h], r14
0x1400b2a27  mov     [rbx+0FB0h], r14d
0x1400b2a2e  mov     [rbx+8CC8h], r14
0x1400b2a35  mov     [rbx+8CD0h], r14
0x1400b2a3c  mov     [rbx+8CD8h], r14d
0x1400b2a43  mov     dword ptr [rbx+8CDCh], 4Eh ; 'N'
0x1400b2a4d  mov     dword ptr [rbx+8CE0h], 47h ; 'G'
0x1400b2a57  mov     [rax+8], rax
0x1400b2a5b  mov     [rax], rax
0x1400b2a5e  lea     rax, [rbx+8CF8h]
0x1400b2a65  mov     [rax+8], rax
0x1400b2a69  mov     [rax], rax
0x1400b2a6c  mov     [rbx+8D28h], r14
0x1400b2a73  mov     [rbx+8D30h], r14
0x1400b2a7a  mov     [rbx+8D38h], r14d
0x1400b2a81  mov     [rbx+8D3Ch], r15d
0x1400b2a88  mov     dword ptr [rbx+8D40h], 0FFFFFFFFh
0x1400b2a92  mov     [rbx+8D98h], r14d
0x1400b2a99  mov     dword ptr [rbx+8DA0h], 101h
0x1400b2aa3  mov     [rbx+8DA4h], r14b
0x1400b2aaa  mov     [rbx+8DB8h], r14
0x1400b2ab1  mov     [rbx+8DC0h], r14
0x1400b2ab8  mov     [rbx+8DC8h], r14d
0x1400b2abf  mov     dword ptr [rbx+8DCCh], 0Ch
0x1400b2ac9  mov     [rbx+8DD0h], r14b
0x1400b2ad0  mov     [rbx+8DD8h], r14
0x1400b2ad7  mov     [rbx+8DE0h], r14
0x1400b2ade  mov     [rbx+8E38h], r14
0x1400b2ae5  mov     [rbx+8E40h], r14
0x1400b2aec  mov     [rbx+8E48h], r14d
0x1400b2af3  mov     dword ptr [rbx+8E4Ch], 4Eh ; 'N'
0x1400b2afd  mov     dword ptr [rbx+8E50h], 2Eh ; '.'
0x1400b2b07  mov     dword ptr [rbx+8E58h], 0FFFFFFFFh
0x1400b2b11  mov     [rbx+8E60h], r14
0x1400b2b18  mov     [rbx+8E68h], r14
0x1400b2b1f  mov     [rbx+8E70h], r14
0x1400b2b26  mov     [rbx+8E78h], r14
0x1400b2b2d  call    memset
0x1400b2b32  and     byte ptr [rbx+9168h], 9Dh
0x1400b2b39  and     byte ptr [rbx+9169h], 0F2h
0x1400b2b40  and     byte ptr [rbx+916Bh], 0FEh
0x1400b2b47  mov     [rbx+9160h], r14d
0x1400b2b4e  mov     [rbx+916Ch], r14w
0x1400b2b56  mov     [rbx+9171h], r14b
0x1400b2b5d  mov     [rbx+91B8h], r14
0x1400b2b64  mov     [rbx+91C0h], r14
0x1400b2b6b  mov     [rbx+91C8h], r14d
0x1400b2b72  mov     [rbx+91CCh], r15d
0x1400b2b79  lea     rcx, [rbx+91D0h]; this
0x1400b2b80  call    ??0DXGK_LOG@@QEAA@XZ; DXGK_LOG::DXGK_LOG(void)
0x1400b2b85  mov     [rbx+91F0h], r14
0x1400b2b8c  lea     rcx, [rbx+9220h]; SpinLock
0x1400b2b93  mov     [rbx+91F8h], r14d
0x1400b2b9a  mov     [rbx+9200h], r14
0x1400b2ba1  mov     [rbx+9208h], r14
0x1400b2ba8  mov     [rbx+9210h], r14d
0x1400b2baf  mov     dword ptr [rbx+9214h], 16h
0x1400b2bb9  mov     dword ptr [rbx+9218h], 42h ; 'B'
0x1400b2bc3  mov     [rcx+8], r14
0x1400b2bc7  call    cs:__imp_KeInitializeSpinLock
0x1400b2bce  nop     dword ptr [rax+rax+00h]
0x1400b2bd3  lea     rcx, [rbx+9240h]
0x1400b2bda  mov     r8b, r15b; State
0x1400b2bdd  mov     [rcx], r14
0x1400b2be0  lea     rax, [rcx+18h]
0x1400b2be4  mov     [rcx+8], r14
0x1400b2be8  xor     edx, edx; Type
0x1400b2bea  mov     [rcx+10h], r14d
0x1400b2bee  mov     [rcx+14h], r15d
0x1400b2bf2  mov     [rcx+28h], r14d
0x1400b2bf6  mov     [rcx+68h], r15d
0x1400b2bfa  mov     [rax+8], rax
0x1400b2bfe  mov     [rax], rax
0x1400b2c01  lea     rax, ?DeferredWorkQueueCallback@DXG_DEFERRED_WORK_QUEUE@@SAXPEAX@Z; DXG_DEFERRED_WORK_QUEUE::DeferredWorkQueueCallback(void *)
0x1400b2c08  mov     [rcx+58h], rax
0x1400b2c0c  mov     [rcx+60h], rcx
0x1400b2c10  mov     [rcx+48h], r14
0x1400b2c14  add     rcx, 30h ; '0'; Event
0x1400b2c18  call    cs:__imp_KeInitializeEvent
0x1400b2c1f  nop     dword ptr [rax+rax+00h]
0x1400b2c24  lea     rcx, [rbx+92B0h]; this
0x1400b2c2b  mov     rdx, rbx; struct VIDMM_GLOBAL *
0x1400b2c2e  call    ??0VIDMM_PURGE_TELEMETRY@@QEAA@PEAVVIDMM_GLOBAL@@@Z; VIDMM_PURGE_TELEMETRY::VIDMM_PURGE_TELEMETRY(VIDMM_GLOBAL *)
0x1400b2c33  lea     rax, [rbx+9F88h]
0x1400b2c3a  mov     [rbx+9F08h], r14d
0x1400b2c41  lea     rcx, [rbx+0A028h]; SpinLock
0x1400b2c48  mov     [rax+8], rax
0x1400b2c4c  mov     [rax], rax
0x1400b2c4f  call    cs:__imp_KeInitializeSpinLock
0x1400b2c56  nop     dword ptr [rax+rax+00h]
0x1400b2c5b  mov     [rbx+0A030h], r14
0x1400b2c62  lea     rcx, [rbx+0A050h]; Event
0x1400b2c69  mov     [rbx+0A038h], r14
0x1400b2c70  mov     r8b, r15b; State
0x1400b2c73  mov     [rbx+0A040h], r14
0x1400b2c7a  xor     edx, edx; Type
0x1400b2c7c  mov     [rbx+0A048h], r14d
0x1400b2c83  mov     [rbx+0A04Ch], r15d
0x1400b2c8a  mov     [rbx+0A068h], r14d
0x1400b2c91  call    cs:__imp_KeInitializeEvent
0x1400b2c98  nop     dword ptr [rax+rax+00h]
0x1400b2c9d  mov     [rbx+0A078h], r14
0x1400b2ca4  mov     [rbx+0A080h], r14
0x1400b2cab  mov     [rbx+0A088h], r14
0x1400b2cb2  mov     [rbx+0A090h], r14
0x1400b2cb9  mov     [rbx+0A098h], r14
0x1400b2cc0  mov     [rbx+0A0A0h], r14
0x1400b2cc7  mov     [rbx+0A0A8h], r14
0x1400b2cce  mov     [rbx+0A0B0h], r14d
0x1400b2cd5  mov     [rbx+0A0B4h], r15d
0x1400b2cdc  mov     dword ptr [rbx+0A0B8h], 0FFFFFFFFh
0x1400b2ce6  mov     [rbx+0A0C0h], r14
0x1400b2ced  mov     [rbx+0A0C8h], r14
0x1400b2cf4  mov     [rbx+0A0D0h], r14d
0x1400b2cfb  mov     dword ptr [rbx+0A0D4h], 7
0x1400b2d05  mov     dword ptr [rbx+0A0D8h], 3Ch ; '<'
0x1400b2d0f  mov     [rbx+0A130h], r14
0x1400b2d16  mov     [rbx+0A138h], r14
0x1400b2d1d  mov     [rbx+0A140h], r14
0x1400b2d24  mov     [rbx+0A148h], r14
0x1400b2d2b  mov     [rbx+0A150h], r14
0x1400b2d32  mov     [rbx+0A158h], r14b
0x1400b2d39  mov     [rbx+0A160h], r14
0x1400b2d40  mov     [rbx+0A168h], r14
0x1400b2d47  mov     [rbx+0A170h], r14d
0x1400b2d4e  mov     dword ptr [rbx+0A174h], 4Eh ; 'N'
0x1400b2d58  mov     dword ptr [rbx+0A178h], 0FFFFFFFFh
0x1400b2d62  mov     [rbx+0A180h], r14b
0x1400b2d69  mov     dword ptr [rbx+0A184h], 0FFFFFFFFh
0x1400b2d73  mov     [rbx+0A198h], r14b
0x1400b2d7a  mov     [rbx+0A1A0h], r14
0x1400b2d81  mov     [rbx+0A1A8h], r14
0x1400b2d88  mov     [rbx+0A1C0h], r14
0x1400b2d8f  mov     [rbx+0A1C8h], r14
0x1400b2d96  lea     rax, [rbx+288h]
0x1400b2d9d  mov     [rbx+0A230h], r14d
0x1400b2da4  mov     edx, r14d
0x1400b2da7  mov     [rbx+0A278h], r14
0x1400b2dae  mov     [rax+8], rax
0x1400b2db2  mov     [rax], rax
0x1400b2db5  lea     rax, [rbx+9EF8h]
0x1400b2dbc  mov     [rax+8], rax
0x1400b2dc0  mov     [rax], rax
0x1400b2dc3  lea     rax, [rbx+9230h]
0x1400b2dca  mov     [rax+8], rax
0x1400b2dce  mov     [rax], rax
0x1400b2dd1  lea     rax, [rbx+298h]
0x1400b2dd8  mov     [rax+8], rax
0x1400b2ddc  mov     [rax], rax
0x1400b2ddf  lea     rax, [rbx+2A8h]
0x1400b2de6  mov     [rax+8], rax
0x1400b2dea  mov     [rax], rax
0x1400b2ded  lea     rax, [rbx+8D18h]
0x1400b2df4  mov     [rax+8], rax
0x1400b2df8  mov     [rax], rax
0x1400b2dfb  lea     rax, [rbx+8D08h]
0x1400b2e02  mov     [rax+8], rax
0x1400b2e06  mov     [rax], rax
0x1400b2e09  lea     rax, [rbx+0A120h]
0x1400b2e10  mov     [rax+8], rax
0x1400b2e14  mov     [rax], rax
0x1400b2e17  lea     rax, [rbx+0A188h]
0x1400b2e1e  mov     [rax+8], rax
0x1400b2e22  mov     [rax], rax
0x1400b2e25  lea     rax, [rbx+8DA8h]
0x1400b2e2c  mov     [rax+8], rax
0x1400b2e30  mov     [rax], rax
0x1400b2e33  mov     rax, rdx
0x1400b2e36  lea     rcx, [rbx+0A0E0h]
0x1400b2e3d  shl     rax, 4
0x1400b2e41  add     rcx, rax
0x1400b2e44  mov     [rax+rbx+0A0E8h], rcx
0x1400b2e4c  lea     rax, [rdx+0A0Eh]
0x1400b2e53  add     rax, rax
0x1400b2e56  add     rdx, r15
0x1400b2e59  mov     [rbx+rax*8], rcx
0x1400b2e5d  cmp     rdx, 4
0x1400b2e61  jnz     short loc_1400B2E33
0x1400b2e63  lea     rcx, [rbx+9EF0h]; SpinLock
0x1400b2e6a  mov     [rbx+0C88h], r14
0x1400b2e71  call    cs:__imp_KeInitializeSpinLock
0x1400b2e78  nop     dword ptr [rax+rax+00h]
0x1400b2e7d  mov     [rsp+48h+Depth], r14w; Depth
0x1400b2e83  lea     rcx, [rbx+8EC0h]; Lookaside
0x1400b2e8a  mov     [rsp+48h+Tag], 61356956h; Tag
0x1400b2e92  xor     r9d, r9d; Flags
0x1400b2e95  xor     r8d, r8d; Free
0x1400b2e98  mov     [rsp+48h+Size], 20h ; ' '; Size
0x1400b2ea1  xor     edx, edx; Allocate
0x1400b2ea3  mov     [rbx+0C28h], r15d
0x1400b2eaa  call    cs:__imp_ExInitializePagedLookasideList
0x1400b2eb1  nop     dword ptr [rax+rax+00h]
0x1400b2eb6  mov     [rbx+0A1B0h], r14
0x1400b2ebd  lea     rax, ?VidMmUpgrade64KBWork@@YAXPEAX@Z; VidMmUpgrade64KBWork(void *)
0x1400b2ec4  mov     [rbx+9FC0h], rax
0x1400b2ecb  lea     rcx, [rbx+8DE8h]; struct VIDMM_PERIODIC_TRIM_DATA *
0x1400b2ed2  mov     [rbx+9FC8h], rbx
0x1400b2ed9  mov     [rbx+9FB0h], r14
0x1400b2ee0  mov     qword ptr [rbx+9FD0h], 2
0x1400b2eeb  mov     dword ptr [rbx+9F78h], 40000h
0x1400b2ef5  call    ?InitializePeriodicTrimData@@YAXPEAUVIDMM_PERIODIC_TRIM_DATA@@@Z; InitializePeriodicTrimData(VIDMM_PERIODIC_TRIM_DATA *)
0x1400b2efa  lea     rcx, [rbx+8E10h]; struct VIDMM_PERIODIC_TRIM_DATA *
0x1400b2f01  call    ?InitializePeriodicTrimData@@YAXPEAUVIDMM_PERIODIC_TRIM_DATA@@@Z; InitializePeriodicTrimData(VIDMM_PERIODIC_TRIM_DATA *)
0x1400b2f06  mov     r14, [rsp+48h+arg_8]
0x1400b2f0b  mov     rax, rbx
0x1400b2f0e  mov     rbx, [rsp+48h+arg_0]
0x1400b2f13  add     rsp, 40h
0x1400b2f17  pop     r15
0x1400b2f19  retn
```
